GEdit actual evaluation setup used in our rebuttal experiments (sanitized)

- Judge backbone: Gemini-2.5-Flash
- VIEScore mode: `tie`
- Dataset: GEdit benchmark (`1212` entries)
- Task types: `background_change`, `color_alter`, `material_alter`, `motion_change`, `ps_human`, `style_change`, `subject-add`, `subject-remove`, `subject-replace`, `text_change`, `tone_transfer`
- Languages: `en`, `cn`
- Image preprocessing: resized to area-equivalent `512x512` while preserving aspect ratio
- Parallel workers: `150`

Evaluation inputs:
- `SC` prompt takes the original image and the edited image, together with the editing instruction
- `PQ` prompt takes only the edited image

Prompt assembly actually used:
- `SC = _context_no_delimit + _prompts_0shot_two_image_edit_rule + _prompts_0shot_tie_rule_SC`
- `PQ = _context_no_delimit + _prompts_0shot_rule_PQ`

Aggregation rule actually used:

```text
SC_score = min(results_dict["SC"]["score"])
PQ_score = min(results_dict["PQ"]["score"])
Overall_score = sqrt(SC_score * PQ_score)
```

That is, `SC` is the minimum of editing-success and overediting, `PQ` is the minimum of naturalness and artifact-free quality, and the final score is their geometric mean.
