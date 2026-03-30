# Anonymous visual supplement for rebuttal

This page provides the qualitative and quantitative evidence referenced in the anonymous rebuttal. It is organized by reviewer concern for quick inspection.

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

### Step-sensitivity summary

| Model | 10-step non-edit L1 | 40-step non-edit L1 | 10-step non-edit LPIPS | 40-step non-edit LPIPS |
| --- | ---: | ---: | ---: | ---: |
| SFT | 3.71 | 3.28 | 0.0316 | 0.0276 |
| TC-FM | 3.32 | 3.03 | 0.0240 | 0.0190 |
| TC-FM+ | **2.88** | **2.18** | **0.0173** | **0.0126** |

### Compositional examples

**Overlap case.** `TC-FM` and `TC-FM+` remain stronger than `SFT` without visible spillover into invariant regions.

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

**Disjoint case.** The same pattern holds on a disjoint compositional instruction.

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

---

## Reviewer mVvh

### Key findings

- These additional qualitative examples make the contribution of regular `TC-FM` directly visible, not only the final `TC-FM+` stage.
- Relative to `SFT`, `TC-FM` already improves non-edited-region preservation and face consistency.
- `TC-FM+` further improves local realism, material texture, and physical plausibility.

### Qualitative examples

**Compositional realism.** Age transformation is materially more realistic.

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

**Face consistency.** The beard is preserved and the face remains more coherent.

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

**Physical plausibility.** Human texture, clothing realism, and shadow structure remain more plausible.

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

---

## Reviewer V9Gq

### Key findings

- Relative to strong closed-source editors, `TC-FM+` is consistently more precise in the targeted edit region.
- It causes fewer unintended changes to pose, layout, wall structure, and background context.
- The advantage is especially visible on compound instructions, where competing models more often satisfy the edit by globally repainting the scene.

### Closed-source comparisons

**Precise localized edit.** Only the targeted ribbon region is edited.

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

**Compound instruction with preservation.** The compound request is satisfied without globally repainting the room structure.

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

---

## Reviewer Dx1H

### Key findings

- The clearest failure modes cluster in two regimes: franchise-specific stylization and large geometric edits such as resizing or aspect-ratio transformation.
- These examples are included to make the limitation boundary explicit rather than leaving it implicit in the rebuttal text.

### Failure cases

**Large geometric edit.** The requested proportion change from square to `3:2` landscape is not completed successfully.

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

**Stylization failure.** The requested Ghibli-like target is not reached convincingly.

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
