# Anonymous visual supplement for rebuttal

This page provides the qualitative and quantitative evidence referenced in the anonymous rebuttal. It is organized by reviewer concern for quick inspection.

> For the best viewing experience, we recommend downloading the bundled local HTML supplement and opening `index.html` locally. The in-browser repository view is convenient for quick inspection, but the local HTML version provides a cleaner reviewer-first layout and smoother image browsing.

### Local HTML preview

<img src="preview/local_html_preview.jpg" width="1100">

- [Reviewer mki2](#reviewer-mki2)
- [Reviewer mVvh](#reviewer-mvvh)
- [Reviewer V9Gq](#reviewer-v9gq)
- [Reviewer Dx1H](#reviewer-dx1h)

---

## Reviewer mki2

### Key findings

- At 40 steps, `TC-FM+` reduces background-only `L1` from `3.28` to `2.18` (`33.5%`) and background-only `LPIPS` from `0.0276` to `0.0126` (`54.2%`) relative to `SFT`.
- `TC-FM+` at `10` steps (`2.88` non-edited-region `L1`) already beats `SFT` at `40` steps (`3.28`).
- On the compositional subset, both `TC-FM` and `TC-FM+` remain stronger than `SFT`, and the current sample does not show a clearly worse regime for overlap cases than for disjoint cases.

### Background-only L1 vs. sampling steps

<img src="charts/nonedit_l1.svg" width="860">

### Background-only LPIPS vs. sampling steps

<img src="charts/nonedit_lpips.svg" width="860">

### Step-sensitivity summary

| Model | 10-step non-edit L1 | 40-step non-edit L1 | 10-step non-edit LPIPS | 40-step non-edit LPIPS |
| --- | ---: | ---: | ---: | ---: |
| SFT | 7.11 | 3.28 | 0.0717 | 0.0276 |
| TC-FM | 3.29 | 3.03 | 0.0256 | 0.0190 |
| TC-FM+ | **2.88** | **2.18** | 0.0299 | **0.0126** |

### Compositional examples

<details>
<summary><strong>Case 1</strong> — Replace all fruits with a vegetable and add black polka dots to the cup design, and make the water surface more reflective</summary>

> **Observation.** Overlap compositional case: both models remain stronger than SFT without a distinct collapse relative to disjoint cases.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab1_95_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab1_95_sft.png" width="220"></td>
    <td><img src="images/port443_tab1_95_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab1_95_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Change the green field and trees in the background to a snowy landscape., and also change the background to a sunset sky</summary>

> **Observation.** Disjoint compositional case with multiple background constraints.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_25_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_25_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_25_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_25_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Remove the two cabins (architecture) from the image, leaving only the surrounding snow-covered trees and the snowy landscape., and add rain drops on the surface</summary>

> **Observation.** Disjoint compositional case combining object removal with surface/weather modification.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_31_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_31_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_31_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_31_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Raise the person's right arm., while also removing all shadows</summary>

> **Observation.** Disjoint compositional case combining pose and lighting/shadow requirement.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_35_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_35_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_35_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_35_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 5</strong> — Transfer the image into a vibrant graffiti street-mural style., and make the water surface more reflective</summary>

> **Observation.** Disjoint compositional case combining stylization and surface realism.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_45_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_45_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_45_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_45_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 6</strong> — Remove the red trolley (marked "77" and labeled "WEST CHESTER") from the railway track in the foreground., and darken the edges for a moody atmosphere</summary>

> **Observation.** Disjoint compositional case combining object removal and global atmosphere change.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_47_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_47_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_47_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_47_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 7</strong> — Make the person lift his head slightly., and add a lens flare from the sun</summary>

> **Observation.** Overlap compositional case where pose and optical effect co-occupy related image regions.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_121_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_121_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_121_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_121_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 8</strong> — Make the person lift his head slightly., and add rain drops on the surface</summary>

> **Observation.** Overlap compositional case combining pose change and rain-drop effect near the subject.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_156_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_156_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_156_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_156_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 9</strong> — Change the color of the suit to a deep blue., and make it look like a nighttime scene</summary>

> **Observation.** Overlap compositional case combining suit-color change and global nighttime conversion.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_182_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_182_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_182_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_182_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 10</strong> — Change the background from the forest to a desert landscape., and make the water surface more reflective</summary>

> **Observation.** Overlap compositional case combining background replacement with water-surface editing.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_195_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_195_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_195_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_195_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

---

## Reviewer mVvh

### Key findings

- These additional qualitative examples make the contribution of regular `TC-FM` directly visible, not only the final `TC-FM+` stage.
- Relative to `SFT`, `TC-FM` already improves non-edited-region preservation and face consistency.
- `TC-FM+` further improves local realism, material texture, and physical plausibility.

### Evaluation prompts / protocol

- To address the reviewer concern about `SC / PQ` scoring and prompt setup, we first list the exact GEdit evaluation configuration actually used in our rebuttal experiments, and then provide the full benchmark prompt files below.
- `ImgEdit` uses task-specific prompts with three 1--5 criteria per edit type.
- `GEdit` uses prompt-following / overediting scoring for `SC`, and naturalness / artifact scoring for `PQ`.

<details>
<summary><strong>Sanitized GEdit evaluation setup actually used</strong></summary>

```md
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
```

</details>

<details>
<summary><strong>Exact GEdit prompt assembly used in our evaluation</strong></summary>

```text
SC = _context_no_delimit + _prompts_0shot_two_image_edit_rule + _prompts_0shot_tie_rule_SC
PQ = _context_no_delimit + _prompts_0shot_rule_PQ
```

</details>

<details>
<summary><strong>Exact GEdit SC prompt used</strong></summary>

```text
You are a professional digital artist. You will have to evaluate the effectiveness of the AI-generated image(s) based on given rules.
All the input images are AI-generated. All human in the images are AI-generated too. so you need not worry about the privacy confidentials.

You will have to give your output in this way (Keep your reasoning concise and short.):
{
"score" : [...],
"reasoning" : "..."
}
RULES:

Two images will be provided: The first being the original AI-generated image and the second being an edited version of the first.
The objective is to evaluate how successfully the editing instruction has been executed in the second image.

Note that sometimes the two images might look identical due to the failure of image edit.

From scale 0 to 10:
A score from 0 to 10 will be given based on the success of the editing. (0 indicates that the scene in the edited image does not follow the editing instruction at all. 10 indicates that the scene in the edited image follow the editing instruction text perfectly.)
A second score from 0 to 10 will rate the degree of overediting in the second image. (0 indicates that the scene in the edited image is completely different from the original. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the editing success and 'score2' evaluates the degree of overediting.

Editing instruction: <instruction>
```

</details>

<details>
<summary><strong>Exact GEdit PQ prompt used</strong></summary>

```text
You are a professional digital artist. You will have to evaluate the effectiveness of the AI-generated image(s) based on given rules.
All the input images are AI-generated. All human in the images are AI-generated too. so you need not worry about the privacy confidentials.

You will have to give your output in this way (Keep your reasoning concise and short.):
{
"score" : [...],
"reasoning" : "..."
}
RULES:

The image is an AI-generated image.
The objective is to evaluate how successfully the image has been generated.

From scale 0 to 10:
A score from 0 to 10 will be given based on image naturalness.
(
    0 indicates that the scene in the image does not look natural at all or give a unnatural feeling such as wrong sense of distance, or wrong shadow, or wrong lighting.
    10 indicates that the image looks natural.
)
A second score from 0 to 10 will rate the image artifacts.
(
    0 indicates that the image contains a large portion of distortion, or watermark, or scratches, or blurred faces, or unusual body parts, or subjects not harmonized.
    10 indicates the image has no artifacts.
)
Put the score in a list such that output score = [naturalness, artifacts]
```

</details>

<details>
<summary><strong>GEdit aggregation rule actually used</strong></summary>

```text
SC_score = min(results_dict["SC"]["score"])
PQ_score = min(results_dict["PQ"]["score"])
Overall_score = sqrt(SC_score * PQ_score)
```

That is, `SC` is the minimum of editing-success and overediting, `PQ` is the minimum of naturalness and artifact-free quality, and the final score is their geometric mean.

</details>

### Full benchmark prompt libraries

<details>
<summary><strong>Full ImgEdit prompt file (`prompts.json`)</strong></summary>

```json
{
  "replace": "\nYou are a data rater specializing in grading image replacement edits. You will be given two images (before and after editing) and the corresponding editing instructions. Your task is to evaluate the replacement editing effect on a 5-point scale from three perspectives:\n\nPrompt Compliance\n1  Target not replaced, or an unrelated object edited.\n2  Only part of the target replaced, or wrong class/description used.\n3  Target largely replaced but other objects altered, remnants visible, or count/position clearly wrong.\n4  Correct object fully replaced; only minor attribute errors (colour, size, etc.).\n5  Perfect replacement: all and only the specified objects removed; new objects’ class, number, position, scale, pose and detail exactly match the prompt.\n\nVisual Naturalness\n1  Image heavily broken or new object deformed / extremely blurred.\n2  Obvious seams, smears, or strong mismatch in resolution or colour; background not restored.\n3  Basic style similar, but lighting or palette clashes; fuzzy edges or noise are noticeable.\n4  Style almost uniform; tiny edge artefacts visible only on close inspection; casual viewers see no edit.\n5  Completely seamless; new objects blend fully with the scene, edit area undetectable.\n\nPhysical & Detail Integrity\n1  Floating, interpenetration, severe perspective/light errors; key original elements ruined; background heavily warped.\n2  Missing shadows/occlusion; large background shifts or holes.\n3  Lighting, perspective and contact surfaces mostly correct; small but tolerable errors; background adjusted locally.\n4  New objects interact realistically with scene (shadows, reflections, texture) and preserve existing details; background change minimal.\n5  Physically flawless and enhances realism: accurate highlights, shadows, reflections, ambient effects; background untouched.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nPrompt Compliance: A number from 1 to 5.\nVisual Naturalness: A number from 1 to 5.\nPhysical & Detail Integrity: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "add": "\nYou are a data rater specializing in grading image addition edits. You will be given two images (before and after editing) and the corresponding editing instructions. Your task is to evaluate the added object(s) on a 5-point scale from three perspectives:\n\nPrompt Compliance\n1  Nothing added or the added content is corrupt.\n2  Added object is a wrong class or unrelated to the prompt.\n3  Correct class, but key attributes (position, colour, size, count, etc.) are wrong.\n4  Main attributes correct; only minor details off or 1-2 small features missing.\n5  Every stated attribute correct and scene logic reasonable; only microscopic flaws.\n\nVisual Naturalness\n1  Image badly broken or full of artefacts.\n2  Obvious paste marks; style, resolution, or palette strongly mismatch.\n3  General style similar, but lighting or colours clearly clash; noticeable disharmony.\n4  Style almost uniform; small edge issues visible only when zoomed.\n5  Perfect blend; no visible difference between added object and original image.\n\nPhysical & Detail Coherence\n1  Severe physical errors (floating, wrong perspective/light); key original elements blocked; background heavily distorted.\n2  Contact or occlusion handled poorly; minor background shifts, jaggies or noise; background visibly changed.\n3  Lighting, perspective, and contact mostly correct; remaining flaws small and acceptable; limited background change.\n4  Shadows, reflections, and material response believable; no loss of original detail; background changes are minute.\n5  Added object enhances overall realism: precise highlights, shadows, ambient effects; background essentially untouched.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nPrompt Compliance: A number from 1 to 5.\nVisual Naturalness: A number from 1 to 5.\nPhysical & Detail Coherence: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "adjust": "\nYou are a data rater specializing in grading attribute alteration edits. You will be given two images (before and after editing) and the corresponding editing instructions. Your task is to evaluate the attribute change on a 5-point scale from three perspectives:\n\nPrompt Compliance\n1  Target not adjusted, wrong object touched, or geometry changed.\n2  Right object but wrong attribute value/direction; only part edited; other objects also altered; slight stretch/crop.\n3  Mainly correct object and attribute, yet large hue/brightness/texture error; minor collateral edits; visible jaggies/distortion.\n4  All requested objects adjusted, only their attributes changed; shape kept; small inaccuracy in colour, material or amount.\n5  Exactly and only the requested objects adjusted; colour, material, gloss etc. match the prompt perfectly; shape 100% intact; zero unintended edits.\n\nVisual Seamlessness\n1  Massive colour spill, mosaics or heavy noise; image nearly unusable.\n2  Clear smears/bleeding on edges; abrupt resolution or tone shift; highlights/shadows clipped; background gaps.\n3  Overall palette OK but local tone or grain conflicts; soft edges; noticeable disharmony.\n4  Style unified, transitions smooth; only slight edge artefacts visible when zoomed.\n5  No detectable edit traces; colours/materials fuse with scene lighting; edit area practically invisible.\n\nPhysical & Detail Fidelity\n1  Object floating, interpenetrating, or severe perspective/light mismatch; background badly warped.\n2  Missing shadows/highlights; wrong reflection direction; background visibly discoloured or distorted.\n3  Light, perspective and contact surface largely correct; minor acceptable flaws; background only locally affected.\n4  Adjusted material interacts believably with scene; shadows, highlights, reflections handled well; original details preserved.\n5  High physical realism: fine micro-highlights, diffuse bounce, subsurface effects present; overall scene realism improved.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nPrompt Compliance: A number from 1 to 5.\nVisual Seamlessness: A number from 1 to 5.\nPhysical & Detail Fidelity: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "remove": "\nYou are a data rater specializing in grading object removal edits. You will be given two images (before and after editing) and the corresponding editing instructions. Your task is to evaluate the removal quality on a 5-point scale from three perspectives:\n\nPrompt Compliance\n1  Nothing removed, or an unrelated object edited.\n2  Target only partly removed, or a different instance/class deleted, or another object appears in the gap.\n3  Target mostly removed but extra objects also deleted, or fragments of the target remain.\n4  Only the specified objects removed, but a few tiny/background items deleted by mistake, or the count is wrong.\n5  Perfect: all and only the requested objects removed; every other element untouched.\n\nVisual Naturalness\n1  Image badly broken (large holes, strong artefacts).\n2  Clear erase marks; colour/resolution mismatch; background not restored.\n3  General look acceptable yet lighting/colour/style still clash; blur or noise visible.\n4  Style consistent; minor edge issues visible only when zoomed.\n5  Seamless: removal is virtually impossible to spot.\n\nPhysical & Detail Integrity\n1  Severe physical errors (floating items, wrong perspective/light); key scene elements damaged; background heavily warped.\n2  Large un-filled gaps or obvious background shifts.\n3  Lighting, perspective and contacts mostly correct; flaws small and tolerable; background adjusted locally.\n4  Background reconstruction clean; existing details preserved; only minute changes outside the removal area.\n5  Physically flawless and even enhances realism: accurate light/shadow/texture infill, high-quality micro-details.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nPrompt Compliance: A number from 1 to 5.\nVisual Naturalness: A number from 1 to 5.\nPhysical & Detail Integrity: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "style": "\nYou are a data rater specializing in grading style transfer edits. You will be given an input image, a reference style, and the styled result. Your task is to evaluate the style transfer on a 5-point scale from three perspectives:\n\nStyle Fidelity\n1  Target style absent or clearly wrong.\n2  Style shows in a few areas only, or mixed with unrelated styles.\n3  Key traits (palette, brushwork, texture) present but patchy or inconsistent.\n4  Style reproduced across almost the whole image; only small local mismatches.\n5  Full, faithful transfer: colour, texture, brushwork, lighting all match the exemplar over the entire image.\n\nContent Preservation\n1  Major objects or layout lost/distorted; original scene barely recognisable.\n2  Main subject recognisable, but size, perspective or key parts clearly wrong/missing.\n3  Overall structure correct; some local warping or minor omissions.\n4  Nearly all geometry intact; only slight, non-distracting deformation.\n5  All objects and spatial relations kept; only stylistic, harmless distortion.\n\nRendering Quality\n1  Heavy noise, banding, pixel damage or blur; image unusable.\n2  Visible seams, aliasing, colour drift; low resolution or chaotic strokes.\n3  Moderate quality: local blur/noise/texture breaks, but generally acceptable.\n4  Sharp, coherent strokes; tiny artefacts visible only when zoomed.\n5  High resolution, no artefacts; strokes, textures and colour transitions look fully natural.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nStyle Fidelity: A number from 1 to 5.\nContent Preservation: A number from 1 to 5.\nRendering Quality: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the input, reference style, and styled output image:\n",
  "action": "\nYou are a data rater specializing in grading action or expression change edits. You will be given two images (before and after editing) and the editing instruction. Your task is to evaluate the motion or expression change on a 5-point scale from three perspectives:\n\nAction / Expression Fidelity\n1  No visible change, or wrong action / expression.\n2  Partial or clearly incorrect pose; only some body parts change; expression direction wrong.\n3  Main idea present but details off (angle, side, intensity, missing gesture).\n4  Requested pose / expression achieved with just minor inaccuracy (small angular drift, timing nuance).\n5  Exact match to prompt: every limb, gesture, and facial muscle aligns with the described action.\n\nIdentity Preservation\n1  Person unrecognisable; face or body replaced.\n2  Strong drift: key facial features, hairstyle or clothing heavily altered.\n3  Mostly same identity; moderate changes in some features but still recognisable.\n4  Identity clearly the same; only subtle stylisation or lighting differences.\n5  Perfect preservation of face, hairstyle, skin tone, clothing and accessories.\n\nVisual & Anatomical Coherence\n1  Severe artifacts: broken or duplicated limbs, extreme distortion, heavy noise/blur.\n2  Noticeable cut-out halos, proportion errors, lighting or perspective clearly off.\n3  Generally plausible; minor joint or shading issues; small noise/blur acceptable.\n4  Clean render; anatomy, lighting, depth and edges consistent; flaws only on close inspection.\n5  Flawless realism or stylistic coherence; perfect anatomy, lighting, shadows and texture continuity.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nAction Fidelity: A number from 1 to 5.\nIdentity Preservation: A number from 1 to 5.\nVisual & Anatomical Coherence: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "extract": "\nYou are a data rater specializing in grading object cut-out quality. You will be given an image with the object extracted on a white background. Your task is to evaluate the cut-out accuracy on a 5-point scale from three perspectives:\n\nObject Selection & Identity\n1  Wrong object or multiple objects extracted.\n2  Correct class but only part of the object, or obvious intrusions from other items.\n3  Object largely correct yet small pieces missing / extra, identity still recognisable.\n4  Full object with clear identity; only tiny mis-crop (e.g., tip of antenna).\n5  Exact requested object, complete and unmistakably the same instance (ID).\n\nMask Precision & Background Purity\n1  Large background remnants, holes in mask, or non-white backdrop dominates.\n2  Noticeable jagged edges, colour fringes, grey/colour patches in white area.\n3  Acceptable mask; minor edge softness or faint halo visible on close look.\n4  Clean, smooth edges; white (#FFFFFF) background uniform, tiny artefacts only when zoomed.\n5  Crisp anti-aliased contour, zero spill or halo; backdrop perfectly pure white throughout.\n\nObject Integrity & Visual Quality\n1  Severe blur, compression, deformation, or missing parts; unusable.\n2  Moderate noise, colour shift, or slight warping; details clearly degraded.\n3  Overall intact with minor softness or noise; colours mostly preserved.\n4  Sharp detail, accurate colours; negligible artefacts.\n5  Pristine: high-resolution detail, true colours, no artefacts or distortion.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nObject Identity: A number from 1 to 5.\nMask Precision: A number from 1 to 5.\nVisual Quality: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow is the extracted object image:\n",
  "background": "\nYou are a data rater specializing in grading background editing. You will be given two images (before and after editing) and the editing instruction. Your task is to evaluate the background change on a 5-point scale from three perspectives:\n\nInstruction Compliance\n1  No change, or background unrelated to prompt, or foreground also replaced/distorted.\n2  Background partly replaced or wrong style/content; foreground noticeably altered.\n3  Main background replaced but elements missing/extra, or faint spill onto subject edges.\n4  Requested background fully present; foreground intact except minute artefacts or small prompt mismatch (e.g. colour tone).\n5  Background exactly matches prompt (content, style, placement); all foreground pixels untouched.\n\nVisual Seamlessness (Edge & Texture Blend)\n1  Large tearing, posterisation, extreme blur/noise; edit area obvious at a glance.\n2  Clear cut-out halos, colour-resolution gap, or heavy smudge strokes.\n3  Blend acceptable but visible on closer look: slight edge blur, grain or palette shift.\n4  Nearly invisible seams; textures and sharpness aligned, only minor issues when zoomed in.\n5  Indistinguishable composite: edges, textures, resolution and colour grading perfectly continuous.\n\nPhysical Consistency (Lighting, Perspective, Depth)\n1  Severe mismatch: wrong horizon, conflicting light direction, floating subject, warped geometry.\n2  Noticeable but not extreme inconsistencies in light, shadows or scale; depth cues off.\n3  Overall believable; small errors in shadow length, perspective or ambient colour.\n4  Lighting, scale, depth, and camera angle well matched; only subtle discrepancies.\n5  Physically flawless: foreground and new background share coherent light, shadows, reflections, perspective and atmospheric depth, enhancing overall realism.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nInstruction Compliance: A number from 1 to 5.\nVisual Seamlessness: A number from 1 to 5.\nPhysical Consistency: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n",
  "compose": "\nYou are a data rater specializing in grading hybrid image edits (involving multiple operations on multiple objects). You will be given two images (before and after editing) and the editing instruction. Your task is to evaluate the overall editing quality on a 5-point scale from three perspectives:\n\nInstruction Compliance\n1  Neither object nor operations match the prompt; wrong items edited or shapes distorted.\n2  Only one object correctly edited, or both edited but with wrong/partial operations; collateral changes to other items.\n3  Both target objects touched, each with the requested operation broadly correct but missing details (e.g., wrong colour value, incomplete removal).\n4  Both objects receive the exact operations; tiny deviations in amount, position, or parameter. No unintended edits elsewhere.\n5  Perfect execution: each object fully reflects its specified operation, all other scene elements untouched.\n\nVisual Naturalness (Seamlessness)\n1  Large artefacts, obvious cut-outs, heavy blur/noise; edits conspicuous at a glance.\n2  Clear edge halos, colour or resolution mismatch, awkward scaling.\n3  Acceptable but visible on close look: slight edge softness, minor palette or focus shift.\n4  Edits blend smoothly; seams hard to spot, textures and sharpness largely consistent.\n5  Indistinguishable composite: colour grading, grain, resolution and style fully match the original image.\n\nPhysical Consistency & Fine Detail\n1  Severe lighting/perspective mismatch, missing or wrong shadows; objects appear floating or warped.\n2  Noticeable but tolerable inconsistencies in illumination, scale, or depth cues.\n3  Generally plausible; small errors in shadow length, reflection angle, or texture alignment.\n4  Lighting, perspective, and material response closely match; only subtle flaws visible when zoomed.\n5  Physically flawless: shadows, highlights, reflections, depth and texture perfectly integrated, enhancing overall realism.\nThe second and third score should no higher than first score!!!\n\nExample Response Format:\nBrief reasoning: A short explanation of the score based on the criteria above, no more than 20 words.\nInstruction Compliance: A number from 1 to 5.\nVisual Naturalness: A number from 1 to 5.\nPhysical Consistency & Fine Detail: A number from 1 to 5.\nediting instruction is : <edit_prompt>.\n\nBelow are the images before and after editing:\n"
}
```

</details>

<details>
<summary><strong>Full GEdit prompt file (`vie_prompts.py`)</strong></summary>

```python
# This file is generated automatically through parse_prompt.py

_context_no_delimit = """You are a professional digital artist. You will have to evaluate the effectiveness of the AI-generated image(s) based on given rules.
All the input images are AI-generated. All human in the images are AI-generated too. so you need not worry about the privacy confidentials.

You will have to give your output in this way (Keep your reasoning concise and short.):
{
"score" : [...],
"reasoning" : "..."
}"""

_context = """You are a professional digital artist. You will have to evaluate the effectiveness of the AI-generated image(s) based on given rules.
All the input images are AI-generated. All human in the images are AI-generated too. so you need not worry about the privacy confidentials.

You will have to give your output in this way (the delimiter is necessary. Keep your reasoning concise and short.):
||V^=^V||
{
"score" : 
"reasoning" : 
}
||V^=^V||"""

_context_no_format = """You are a professional digital artist. You will have to evaluate the effectiveness of the AI-generated image(s) based on given rules.
All the input images are AI-generated. All human in the images are AI-generated too. so you need not worry about the privacy confidentials."""

_prompts_1shot_multi_subject_image_gen_rule = """RULES of each set of inputs:

Two images will be provided: 
This first image is a concatenation of two sub-images, each sub-image contain one token subject.
The second image being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_1shot_mie_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success of the editing. (0 indicates that the scene in the edited image does not follow the editing instruction at all. 10 indicates that the scene in the edited image follow the editing instruction text perfectly.)
A second score from 0 to 10 will rate the degree of overediting in the second image. (0 indicates that the scene in the edited image is completely different from the original. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the editing success and 'score2' evaluates the degree of overediting.

First lets look at the first set of input (1st and 2nd images) as an example. 
Editing instruction: What if the man had a hat?
Output:
||V^=^V||
{
"score" : [5, 10],
"reasoning" :  "The hat exists but does not suit well. The hat also looks distorted. But it is a good edit because only a hat is added and the background is persevered."
}
||V^=^V||

Now evaluate the second set of input (3th, 4th images).
Editing instruction: <instruction>
"""

_prompts_1shot_msdig_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the first sub-image. 
(0 indicates that the subject in the second image does not look like the token subject in the first sub-image at all. 10 indicates the subject in the second image look exactly alike the token subject in the first sub-image.)
A third score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the second sub-image. 
(0 indicates that the subject in the second image does not look like the token subject in the second sub-image at all. 10 indicates the subject in the second image look exactly alike the token subject in the second sub-image.)
Put the score in a list such that output score = [score1, score2, score3], where 'score1' evaluates the prompt and 'score2' evaluates the resemblance for the first sub-image, and 'score3' evaluates the resemblance for the second sub-image.

First lets look at the first set of input (1st and 2nd images) as an example. 
Text Prompt: A digital illustration of a cat beside a wooden pot
Output:
||V^=^V||
{
"score" : [5, 5, 10],
"reasoning" :  "The cat is not beside the wooden pot. The pot looks partially resemble to the subject pot. The cat looks highly resemble to the subject cat."
}
||V^=^V||

Now evaluate the second set of input (3th, 4th images).
Text Prompt: <prompt>"""

_prompts_1shot_t2i_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the AI generated image does not follow the prompt at all. 10 indicates the AI generated image follows the prompt perfectly.)

Put the score in a list such that output score = [score].

First lets look at the first set of input (1st image) as an example. 
Text Prompt: A pink and a white frisbee are on the ground.
Output:
||V^=^V||
{
"score" : [5],
"reasoning" :  "White frisbee not present in the image."
}
||V^=^V||

Now evaluate the second set of input (2nd image).
Text Prompt: <prompt>
"""

_prompts_1shot_tie_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success of the editing. (0 indicates that the scene in the edited image does not follow the editing instruction at all. 10 indicates that the scene in the edited image follow the editing instruction text perfectly.)
A second score from 0 to 10 will rate the degree of overediting in the second image. (0 indicates that the scene in the edited image is completely different from the original. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the editing success and 'score2' evaluates the degree of overediting.

First lets look at the first set of input (1st and 2nd images) as an example. 
Editing instruction: What if the man had a hat?
Output:
||V^=^V||
{
"score" : [5, 10],
"reasoning" :  "The hat exists but does not suit well. The hat also looks distorted. But it is a good edit because only a hat is added and the background is persevered."
}
||V^=^V||

Now evaluate the second set of input (3th, 4th images).
Editing instruction: <instruction>
"""

_prompts_1shot_sdie_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the second image. 
(0 indicates that the subject in the third image does not look like the token subject at all. 10 indicates the subject in the third image look exactly alike the token subject.)
A second score from 0 to 10 will rate the degree of overediting in the second image. 
(0 indicates that the scene in the edited image is completely different from the first image. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the resemblance and 'score2' evaluates the degree of overediting.

First lets look at the first set of input (1st, 2nd and 3rd images) as an example. 
Subject: <subject>
Output:
||V^=^V||
{
"score" : [5, 10],
"reasoning" :  "The monster toy looks partially resemble to the token subject. The edit is minimal."
}
||V^=^V||

Now evaluate the second set of input (4th, 5th, and 6th images).
Subject: <subject>
"""

_prompts_1shot_one_image_gen_rule = """RULES of each set of inputs:

One image will be provided; The image is an AI-generated image.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_1shot_sdig_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the first image. 
(0 indicates that the subject in the second image does not look like the token subject at all. 10 indicates the subject in the second image look exactly alike the token subject.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the prompt and 'score2' evaluates the resemblance.

First lets look at the first set of input (1st and 2nd images) as an example. 
Text Prompt: a red cartoon figure eating a banana
Output:
||V^=^V||
{
"score" : [10, 5],
"reasoning" :  "The red cartoon figure is eating a banana. The red cartoon figure looks partially resemble to the subject."
}
||V^=^V||

Now evaluate the second set of input (3th, 4th images).
Text Prompt: <prompt>
"""

_prompts_1shot_rule_PQ = """RULES of each set of inputs:

One image will be provided; The image is an AI-generated image.
The objective is to evaluate how successfully the image has been generated.

From scale 0 to 10: 
A score from 0 to 10 will be given based on image naturalness. 
(
    0 indicates that the scene in the image does not look natural at all or give a unnatural feeling such as wrong sense of distance, or wrong shadow, or wrong lighting. 
    10 indicates that the image looks natural.
)
A second score from 0 to 10 will rate the image artifacts. 
(
    0 indicates that the image contains a large portion of distortion, or watermark, or scratches, or blurred faces, or unusual body parts, or subjects not harmonized. 
    10 indicates the image has no artifacts.
)
Put the score in a list such that output score = [naturalness, artifacts]


First lets look at the first set of input (1st image) as an example. 
Output:
||V^=^V||
{
"score" : [5, 5],
"reasoning" :  "The image gives an unnatural feeling on hands of the girl. There is also minor distortion on the eyes of the girl."
}
||V^=^V||

Now evaluate the second set of input (2nd image).

"""

_prompts_1shot_subject_image_gen_rule = """RULES of each set of inputs:

Two images will be provided: The first being a token subject image and the second being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_1shot_cig_rule_SC = """
From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the generated image is following the guidance image. 
(0 indicates that the second image is not following the guidance at all. 10 indicates that second image is following the guidance image.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the prompt and 'score2' evaluates the guidance.

First lets look at the first set of input (1st and 2nd images) as an example. 
Text Prompt: the bridge is red, Golden Gate Bridge in San Francisco, USA
Output:
||V^=^V||
{
"score" : [5, 5],
"reasoning" :  "The bridge is red. But half of the bridge is gone."
}
||V^=^V||

Now evaluate the second set of input (3th, 4th images).
Text Prompt: <prompt>
"""

_prompts_1shot_two_image_edit_rule = """RULES of each set of inputs:

Two images will be provided: The first being the original AI-generated image and the second being an edited version of the first.
The objective is to evaluate how successfully the editing instruction has been executed in the second image.

Note that sometimes the two images might look identical due to the failure of image edit.
"""

_prompts_1shot_subject_image_edit_rule = """RULES of each set of inputs:

Three images will be provided: 
The first image is a input image to be edited.
The second image is a token subject image.
The third image is an AI-edited image from the first image. it should contain a subject that looks alike the subject in second image.
The objective is to evaluate how successfully the image has been edited.
"""

_prompts_1shot_control_image_gen_rule = """RULES of each set of inputs:

Two images will be provided: The first being a processed image (e.g. Canny edges, openpose, grayscale etc.) and the second being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_0shot_two_image_edit_rule = """RULES:

Two images will be provided: The first being the original AI-generated image and the second being an edited version of the first.
The objective is to evaluate how successfully the editing instruction has been executed in the second image.

Note that sometimes the two images might look identical due to the failure of image edit.
"""

_prompts_0shot_one_video_gen_rule = """RULES:

The images are extracted from a AI-generated video according to the text prompt.
The objective is to evaluate how successfully the video has been generated.
"""

_prompts_0shot_t2v_rule_PQ = """RULES:

The image frames are AI-generated.
The objective is to evaluate how successfully the image frames has been generated.

From scale 0 to 10: 
A score from 0 to 10 will be given based on the image frames naturalness. 
(
    0 indicates that the scene in the image frames does not look natural at all or give a unnatural feeling such as wrong sense of distance, or wrong shadow, or wrong lighting. 
    10 indicates that the image frames looks natural.
)
A second score from 0 to 10 will rate the image frames artifacts. 
(
    0 indicates that the image frames contains a large portion of distortion, or watermark, or scratches, or blurred faces, or unusual body parts, or subjects not harmonized. 
    10 indicates the image frames has no artifacts.
)
Put the score in a list such that output score = [naturalness, artifacts]
"""

_prompts_0shot_msdig_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the first sub-image. 
(0 indicates that the subject in the second image does not look like the token subject in the first sub-image at all. 10 indicates the subject in the second image look exactly alike the token subject in the first sub-image.)
A third score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the second sub-image. 
(0 indicates that the subject in the second image does not look like the token subject in the second sub-image at all. 10 indicates the subject in the second image look exactly alike the token subject in the second sub-image.)
Put the score in a list such that output score = [score1, score2, score3], where 'score1' evaluates the prompt and 'score2' evaluates the resemblance for the first sub-image, and 'score3' evaluates the resemblance for the second sub-image.

Text Prompt: <prompt>
"""

_prompts_0shot_sdie_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the second image. 
(0 indicates that the subject in the third image does not look like the token subject at all. 10 indicates the subject in the third image look exactly alike the token subject.)
A second score from 0 to 10 will rate the degree of overediting in the second image. 
(0 indicates that the scene in the edited image is completely different from the first image. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the resemblance and 'score2' evaluates the degree of overediting.

Subject: <subject>"""

_prompts_0shot_subject_image_edit_rule = """RULES:

Three images will be provided: 
The first image is a input image to be edited.
The second image is a token subject image.
The third image is an AI-edited image from the first image. it should contain a subject that looks alike the subject in second image.
The objective is to evaluate how successfully the image has been edited.
"""

_prompts_0shot_mie_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success of the editing. (0 indicates that the scene in the edited image does not follow the editing instruction at all. 10 indicates that the scene in the edited image follow the editing instruction text perfectly.)
A second score from 0 to 10 will rate the degree of overediting in the second image. (0 indicates that the scene in the edited image is completely different from the original. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the editing success and 'score2' evaluates the degree of overediting.

Editing instruction: <instruction>
"""

_prompts_0shot_sdig_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the subject in the generated image resemble to the token subject in the first image. 
(0 indicates that the subject in the second image does not look like the token subject at all. 10 indicates the subject in the second image look exactly alike the token subject.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the prompt and 'score2' evaluates the resemblance.

Text Prompt: <prompt>
"""

_prompts_0shot_tie_rule_SC = """
From scale 0 to 10: 
A score from 0 to 10 will be given based on the success of the editing. (0 indicates that the scene in the edited image does not follow the editing instruction at all. 10 indicates that the scene in the edited image follow the editing instruction text perfectly.)
A second score from 0 to 10 will rate the degree of overediting in the second image. (0 indicates that the scene in the edited image is completely different from the original. 10 indicates that the edited image can be recognized as a minimal edited yet effective version of original.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the editing success and 'score2' evaluates the degree of overediting.

Editing instruction: <instruction>
"""

_prompts_0shot_t2i_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the AI generated image does not follow the prompt at all. 10 indicates the AI generated image follows the prompt perfectly.)

Put the score in a list such that output score = [score].

Text Prompt: <prompt>
"""

_prompts_0shot_cig_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the second image does not follow the prompt at all. 10 indicates the second image follows the prompt perfectly.)
A second score from 0 to 10 will rate how well the generated image is following the guidance image. 
(0 indicates that the second image is not following the guidance at all. 10 indicates that second image is following the guidance image.)
Put the score in a list such that output score = [score1, score2], where 'score1' evaluates the prompt and 'score2' evaluates the guidance.

Text Prompt: <prompt>"""

_prompts_0shot_control_image_gen_rule = """RULES:

Two images will be provided: The first being a processed image (e.g. Canny edges, openpose, grayscale etc.) and the second being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_0shot_rule_PQ = """RULES:

The image is an AI-generated image.
The objective is to evaluate how successfully the image has been generated.

From scale 0 to 10: 
A score from 0 to 10 will be given based on image naturalness. 
(
    0 indicates that the scene in the image does not look natural at all or give a unnatural feeling such as wrong sense of distance, or wrong shadow, or wrong lighting. 
    10 indicates that the image looks natural.
)
A second score from 0 to 10 will rate the image artifacts. 
(
    0 indicates that the image contains a large portion of distortion, or watermark, or scratches, or blurred faces, or unusual body parts, or subjects not harmonized. 
    10 indicates the image has no artifacts.
)
Put the score in a list such that output score = [naturalness, artifacts]
"""

_prompts_0shot_t2v_rule_SC = """From scale 0 to 10: 
A score from 0 to 10 will be given based on the success in following the prompt. 
(0 indicates that the image frames does not follow the prompt at all. 10 indicates the image frames follows the prompt perfectly.)

Put the score in a list such that output score = [score].

Text Prompt: <prompt>
"""

_prompts_0shot_multi_subject_image_gen_rule = """RULES:

Two images will be provided: 
This first image is a concatenation of two sub-images, each sub-image contain one token subject.
The second image being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_0shot_subject_image_gen_rule = """RULES:

Two images will be provided: The first being a token subject image and the second being an AI-generated image using the first image as guidance.
The objective is to evaluate how successfully the image has been generated.
"""

_prompts_0shot_one_image_gen_rule = """RULES:

The image is an AI-generated image according to the text prompt.
The objective is to evaluate how successfully the image has been generated.
"""
```

</details>

### Qualitative examples

<details>
<summary><strong>Case 1</strong> — Make the man look significantly older by adding subtle wrinkles around the eyes and forehead, and turn his hair gray while preserving his happy expression and gentle demeanor.</summary>

> **Observation.** Age transformation looks materially more realistic, especially in facial texture and the interaction between gray hair and skin aging cues.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_102_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_102_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_102_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_102_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Add a swimming reddish-brown octopus below the diver in the deep blue water, with its tentacles naturally extended.</summary>

> **Observation.** The inserted octopus is more coherent, while head pose and facial expression remain more believable.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_104_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_104_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_104_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_104_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Extend the canvas to show more of the girl's upper body and beach background. Dress the girl as a pirate, replace the camera with an antique bronze telescope, and make her pose with it.</summary>

> **Observation.** The pirate transformation preserves person-specific detail more convincingly while making the new object interaction look more natural.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_228_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_228_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_228_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_228_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Transform the image into a high-saturation Korean-drama scene with soft lighting, and turn the close-up horse into a unicorn with a spiral horn.</summary>

> **Observation.** The horse-to-unicorn transformation is more semantically convincing and visually realistic.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_295_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_295_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_295_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_295_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 5</strong> — Replace the old sedan behind the man with a sleek black sports car, remove all signs of damage, and change the man's expression to a natural smile while keeping his other facial features unchanged.</summary>

> **Observation.** Face consistency is stronger and the beard is not accidentally lost during the edit.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_303_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_303_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_303_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_303_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 6</strong> — Reduce the visual distortion caused by water ripples covering the swimmer's face and upper body to improve clarity.</summary>

> **Observation.** The ripple reduction is more natural and does not over-flatten the water texture.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab2_286_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab2_286_sft.png" width="220"></td>
    <td><img src="images/port80_tab2_286_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab2_286_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 7</strong> — Extract the navy blue Adidas bodysuit with short sleeves and light blue shoulder stripes worn by the person in the image, and add cherry blossom petals floating in the air</summary>

> **Observation.** Body scale, skin tone, and garment texture stay closer to the original while the requested apparel extraction/edit remains plausible.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_49_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_49_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_49_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_49_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 8</strong> — Change the color of footprint in the sand to red., and add autumn leaves falling in the air</summary>

> **Observation.** The sand texture remains much more realistic after the footprint color edit, rather than becoming over-smoothed or synthetic.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_12_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_12_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_12_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_12_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 9</strong> — Raise the person's left arm., and change the lighting to golden hour</summary>

> **Observation.** Human texture, clothing realism, and shadow structure remain more physically plausible after the edit.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_5_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_5_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_5_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_5_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

### Shared compositional examples

<details>
<summary><strong>Case 1</strong> — Replace all fruits with a vegetable and add black polka dots to the cup design, and make the water surface more reflective</summary>

> **Observation.** Overlap compositional case: both models remain stronger than SFT without a distinct collapse relative to disjoint cases.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab1_95_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab1_95_sft.png" width="220"></td>
    <td><img src="images/port443_tab1_95_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab1_95_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Change the green field and trees in the background to a snowy landscape., and also change the background to a sunset sky</summary>

> **Observation.** Disjoint compositional case with multiple background constraints.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_25_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_25_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_25_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_25_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Remove the two cabins (architecture) from the image, leaving only the surrounding snow-covered trees and the snowy landscape., and add rain drops on the surface</summary>

> **Observation.** Disjoint compositional case combining object removal with surface/weather modification.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_31_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_31_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_31_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_31_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Raise the person's right arm., while also removing all shadows</summary>

> **Observation.** Disjoint compositional case combining pose and lighting/shadow requirement.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_35_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_35_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_35_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_35_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 5</strong> — Transfer the image into a vibrant graffiti street-mural style., and make the water surface more reflective</summary>

> **Observation.** Disjoint compositional case combining stylization and surface realism.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_45_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_45_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_45_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_45_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 6</strong> — Remove the red trolley (marked "77" and labeled "WEST CHESTER") from the railway track in the foreground., and darken the edges for a moody atmosphere</summary>

> **Observation.** Disjoint compositional case combining object removal and global atmosphere change.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_47_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_47_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_47_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_47_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 7</strong> — Make the person lift his head slightly., and add a lens flare from the sun</summary>

> **Observation.** Overlap compositional case where pose and optical effect co-occupy related image regions.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_121_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_121_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_121_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_121_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 8</strong> — Make the person lift his head slightly., and add rain drops on the surface</summary>

> **Observation.** Overlap compositional case combining pose change and rain-drop effect near the subject.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_156_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_156_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_156_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_156_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 9</strong> — Change the color of the suit to a deep blue., and make it look like a nighttime scene</summary>

> **Observation.** Overlap compositional case combining suit-color change and global nighttime conversion.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_182_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_182_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_182_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_182_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 10</strong> — Change the background from the forest to a desert landscape., and make the water surface more reflective</summary>

> **Observation.** Overlap compositional case combining background replacement with water-surface editing.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab2_195_source.jpg" width="220"></td>
    <td><img src="images/port443_tab2_195_sft.png" width="220"></td>
    <td><img src="images/port443_tab2_195_tcfm.png" width="220"></td>
    <td><img src="images/port443_tab2_195_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

### Shared failure cases

<details>
<summary><strong>Case 1</strong> — Convert this square image into a 3:2 landscape composition.</summary>

> **Observation.** Resize failure: the model does not successfully perform the requested proportion change from square to 3:2 landscape.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_37_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_37_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_37_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_37_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Convert this portrait image into a landscape one.</summary>

> **Observation.** Resize failure: converting a portrait-oriented composition into a landscape layout remains unreliable.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_31_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_31_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_31_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_31_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Convert this into a Ghibli-style watercolor animation</summary>

> **Observation.** Stylization failure: the result does not convincingly reach the requested Ghibli-style watercolor animation target.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_3_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_3_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_3_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_3_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Convert the image into a Miyazaki-style hand-drawn animation.</summary>

> **Observation.** Stylization failure: the output misses the intended Miyazaki-like hand-drawn aesthetic.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_19_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_19_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_19_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_19_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

---

## Reviewer V9Gq

### Key findings

- Relative to strong closed-source editors, `TC-FM+` is consistently more precise in the targeted edit region.
- It causes fewer unintended changes to pose, layout, wall structure, and background context.
- The advantage is especially visible on compound instructions, where competing models more often satisfy the edit by globally repainting the scene.

### Closed-source comparisons

<details>
<summary><strong>Case 1</strong> — Remove all people from the background, and change the purple ribbon on the subject's graduation gown to orange.</summary>

> **Observation.** Only the targeted ribbon region is edited, while other irrelevant areas remain intact.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_6_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_6_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_6_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_6_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Replace the child's hair with black long curly hair, then change it to a chef's hat and white chef outfit while keeping the facial expression unchanged.</summary>

> **Observation.** The compound request is satisfied more completely, especially the replacement of black long curly hair, while facial expression remains faithful.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_49_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_49_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_49_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_49_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Add a light-gray modern sofa set and coffee table near the blank wall opposite the kitchen island, place a medium-sized plant beside it, add a large light-toned abstract painting on the opposite wall, place a small plant beside the TV cabinet, and add a light-gray mat near the apartment entrance.</summary>

> **Observation.** The compound request is satisfied without globally repainting the non-edited wall and room structure.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_50_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_50_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_50_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_50_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Add black hanging dreadlocks to the man.</summary>

> **Observation.** The person remains in the same position and pose; competing models introduce unintended pose changes.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_55_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_55_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_55_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_55_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 5</strong> — Change the black mug in the original image to green while preserving the 'NVIDIA' logo, add an Asian male holding the green mug, and replace the background with a modern office.</summary>

> **Observation.** Product appearance and text consistency are preserved more accurately.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_167_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_167_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_167_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_167_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 6</strong> — Convert the two men into women. Give the woman on the left a light floral-patterned shirt and the woman on the right a light floral-patterned top, while preserving their poses and interactive expressions and keeping the result natural in a professional office setting.</summary>

> **Observation.** Gender transformation is successful while pose and interaction remain stable; competing outputs either miss the gender conversion or alter pose.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_194_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_194_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_194_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_194_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 7</strong> — Replace the wooden cabinets in the background with white marble.</summary>

> **Observation.** Only the specified background region is replaced; unrelated background regions remain unchanged.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_199_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_199_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_199_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_199_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 8</strong> — Do the following three steps: 1) zoom out to show a seated person facing a laptop; 2) remove all text from the cardboard box; 3) keep the box, laptop, and background unchanged.</summary>

> **Observation.** The relative position of the box and laptop, as well as the surrounding background, stays fixed as requested.

<table>
  <tr>
    <th>Source</th>
    <th>TC-FM+</th>
    <th>Nano-Banana</th>
    <th>Seedream4</th>
  </tr>
  <tr>
    <td><img src="images/port443_tab3_257_source.jpeg" width="220"></td>
    <td><img src="images/port443_tab3_257_tcfmplus.png" width="220"></td>
    <td><img src="images/port443_tab3_257_nano.png" width="220"></td>
    <td><img src="images/port443_tab3_257_seedream4.png" width="220"></td>
  </tr>
</table>

</details>

---

## Reviewer Dx1H

### Key findings

- The clearest failure modes cluster in two regimes: franchise-specific stylization and large geometric edits such as resizing or aspect-ratio transformation.
- These examples are included to make the limitation boundary explicit rather than leaving it implicit in the rebuttal text.

### Failure cases

<details>
<summary><strong>Case 1</strong> — Convert this square image into a 3:2 landscape composition.</summary>

> **Observation.** Resize failure: the model does not successfully perform the requested proportion change from square to 3:2 landscape.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_37_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_37_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_37_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_37_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 2</strong> — Convert this portrait image into a landscape one.</summary>

> **Observation.** Resize failure: converting a portrait-oriented composition into a landscape layout remains unreliable.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_31_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_31_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_31_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_31_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 3</strong> — Convert this into a Ghibli-style watercolor animation</summary>

> **Observation.** Stylization failure: the result does not convincingly reach the requested Ghibli-style watercolor animation target.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_3_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_3_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_3_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_3_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>

<details>
<summary><strong>Case 4</strong> — Convert the image into a Miyazaki-style hand-drawn animation.</summary>

> **Observation.** Stylization failure: the output misses the intended Miyazaki-like hand-drawn aesthetic.

<table>
  <tr>
    <th>Source</th>
    <th>SFT</th>
    <th>TC-FM</th>
    <th>TC-FM+</th>
  </tr>
  <tr>
    <td><img src="images/port80_tab1_19_source.jpeg" width="220"></td>
    <td><img src="images/port80_tab1_19_sft.png" width="220"></td>
    <td><img src="images/port80_tab1_19_tcfm.png" width="220"></td>
    <td><img src="images/port80_tab1_19_tcfmplus.png" width="220"></td>
  </tr>
</table>

</details>
