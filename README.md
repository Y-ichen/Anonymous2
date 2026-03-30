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
<summary><strong>Case 1</strong></summary>

**Prompt.** Replace all fruits with a vegetable and add black polka dots to the cup design, and make the water surface more reflective

**Observation.** Overlap compositional case: both models remain stronger than SFT without a distinct collapse relative to disjoint cases.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Change the green field and trees in the background to a snowy landscape., and also change the background to a sunset sky

**Observation.** Disjoint compositional case with multiple background constraints.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Remove the two cabins (architecture) from the image, leaving only the surrounding snow-covered trees and the snowy landscape., and add rain drops on the surface

**Observation.** Disjoint compositional case combining object removal with surface/weather modification.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Raise the person's right arm., while also removing all shadows

**Observation.** Disjoint compositional case combining pose and lighting/shadow requirement.

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
<summary><strong>Case 5</strong></summary>

**Prompt.** Transfer the image into a vibrant graffiti street-mural style., and make the water surface more reflective

**Observation.** Disjoint compositional case combining stylization and surface realism.

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
<summary><strong>Case 6</strong></summary>

**Prompt.** Remove the red trolley (marked "77" and labeled "WEST CHESTER") from the railway track in the foreground., and darken the edges for a moody atmosphere

**Observation.** Disjoint compositional case combining object removal and global atmosphere change.

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
<summary><strong>Case 7</strong></summary>

**Prompt.** Make the person lift his head slightly., and add a lens flare from the sun

**Observation.** Overlap compositional case where pose and optical effect co-occupy related image regions.

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
<summary><strong>Case 8</strong></summary>

**Prompt.** Make the person lift his head slightly., and add rain drops on the surface

**Observation.** Overlap compositional case combining pose change and rain-drop effect near the subject.

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
<summary><strong>Case 9</strong></summary>

**Prompt.** Change the color of the suit to a deep blue., and make it look like a nighttime scene

**Observation.** Overlap compositional case combining suit-color change and global nighttime conversion.

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
<summary><strong>Case 10</strong></summary>

**Prompt.** Change the background from the forest to a desert landscape., and make the water surface more reflective

**Observation.** Overlap compositional case combining background replacement with water-surface editing.

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

### Qualitative examples

<details>
<summary><strong>Case 1</strong></summary>

**Prompt.** Make the man look significantly older by adding subtle wrinkles around the eyes and forehead, and turn his hair gray while preserving his happy expression and gentle demeanor.

**Observation.** Age transformation looks materially more realistic, especially in facial texture and the interaction between gray hair and skin aging cues.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Add a swimming reddish-brown octopus below the diver in the deep blue water, with its tentacles naturally extended.

**Observation.** The inserted octopus is more coherent, while head pose and facial expression remain more believable.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Extend the canvas to show more of the girl's upper body and beach background. Dress the girl as a pirate, replace the camera with an antique bronze telescope, and make her pose with it.

**Observation.** The pirate transformation preserves person-specific detail more convincingly while making the new object interaction look more natural.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Transform the image into a high-saturation Korean-drama scene with soft lighting, and turn the close-up horse into a unicorn with a spiral horn.

**Observation.** The horse-to-unicorn transformation is more semantically convincing and visually realistic.

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
<summary><strong>Case 5</strong></summary>

**Prompt.** Replace the old sedan behind the man with a sleek black sports car, remove all signs of damage, and change the man's expression to a natural smile while keeping his other facial features unchanged.

**Observation.** Face consistency is stronger and the beard is not accidentally lost during the edit.

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
<summary><strong>Case 6</strong></summary>

**Prompt.** Reduce the visual distortion caused by water ripples covering the swimmer's face and upper body to improve clarity.

**Observation.** The ripple reduction is more natural and does not over-flatten the water texture.

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
<summary><strong>Case 7</strong></summary>

**Prompt.** Extract the navy blue Adidas bodysuit with short sleeves and light blue shoulder stripes worn by the person in the image, and add cherry blossom petals floating in the air

**Observation.** Body scale, skin tone, and garment texture stay closer to the original while the requested apparel extraction/edit remains plausible.

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
<summary><strong>Case 8</strong></summary>

**Prompt.** Change the color of footprint in the sand to red., and add autumn leaves falling in the air

**Observation.** The sand texture remains much more realistic after the footprint color edit, rather than becoming over-smoothed or synthetic.

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
<summary><strong>Case 9</strong></summary>

**Prompt.** Raise the person's left arm., and change the lighting to golden hour

**Observation.** Human texture, clothing realism, and shadow structure remain more physically plausible after the edit.

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
<summary><strong>Case 1</strong></summary>

**Prompt.** Replace all fruits with a vegetable and add black polka dots to the cup design, and make the water surface more reflective

**Observation.** Overlap compositional case: both models remain stronger than SFT without a distinct collapse relative to disjoint cases.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Change the green field and trees in the background to a snowy landscape., and also change the background to a sunset sky

**Observation.** Disjoint compositional case with multiple background constraints.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Remove the two cabins (architecture) from the image, leaving only the surrounding snow-covered trees and the snowy landscape., and add rain drops on the surface

**Observation.** Disjoint compositional case combining object removal with surface/weather modification.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Raise the person's right arm., while also removing all shadows

**Observation.** Disjoint compositional case combining pose and lighting/shadow requirement.

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
<summary><strong>Case 5</strong></summary>

**Prompt.** Transfer the image into a vibrant graffiti street-mural style., and make the water surface more reflective

**Observation.** Disjoint compositional case combining stylization and surface realism.

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
<summary><strong>Case 6</strong></summary>

**Prompt.** Remove the red trolley (marked "77" and labeled "WEST CHESTER") from the railway track in the foreground., and darken the edges for a moody atmosphere

**Observation.** Disjoint compositional case combining object removal and global atmosphere change.

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
<summary><strong>Case 7</strong></summary>

**Prompt.** Make the person lift his head slightly., and add a lens flare from the sun

**Observation.** Overlap compositional case where pose and optical effect co-occupy related image regions.

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
<summary><strong>Case 8</strong></summary>

**Prompt.** Make the person lift his head slightly., and add rain drops on the surface

**Observation.** Overlap compositional case combining pose change and rain-drop effect near the subject.

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
<summary><strong>Case 9</strong></summary>

**Prompt.** Change the color of the suit to a deep blue., and make it look like a nighttime scene

**Observation.** Overlap compositional case combining suit-color change and global nighttime conversion.

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
<summary><strong>Case 10</strong></summary>

**Prompt.** Change the background from the forest to a desert landscape., and make the water surface more reflective

**Observation.** Overlap compositional case combining background replacement with water-surface editing.

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
<summary><strong>Case 1</strong></summary>

**Prompt.** Convert this square image into a 3:2 landscape composition.

**Observation.** Resize failure: the model does not successfully perform the requested proportion change from square to 3:2 landscape.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Convert this portrait image into a landscape one.

**Observation.** Resize failure: converting a portrait-oriented composition into a landscape layout remains unreliable.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Convert this into a Ghibli-style watercolor animation

**Observation.** Stylization failure: the result does not convincingly reach the requested Ghibli-style watercolor animation target.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Convert the image into a Miyazaki-style hand-drawn animation.

**Observation.** Stylization failure: the output misses the intended Miyazaki-like hand-drawn aesthetic.

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
<summary><strong>Case 1</strong></summary>

**Prompt.** Remove all people from the background, and change the purple ribbon on the subject's graduation gown to orange.

**Observation.** Only the targeted ribbon region is edited, while other irrelevant areas remain intact.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Replace the child's hair with black long curly hair, then change it to a chef's hat and white chef outfit while keeping the facial expression unchanged.

**Observation.** The compound request is satisfied more completely, especially the replacement of black long curly hair, while facial expression remains faithful.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Add a light-gray modern sofa set and coffee table near the blank wall opposite the kitchen island, place a medium-sized plant beside it, add a large light-toned abstract painting on the opposite wall, place a small plant beside the TV cabinet, and add a light-gray mat near the apartment entrance.

**Observation.** The compound request is satisfied without globally repainting the non-edited wall and room structure.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Add black hanging dreadlocks to the man.

**Observation.** The person remains in the same position and pose; competing models introduce unintended pose changes.

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
<summary><strong>Case 5</strong></summary>

**Prompt.** Change the black mug in the original image to green while preserving the 'NVIDIA' logo, add an Asian male holding the green mug, and replace the background with a modern office.

**Observation.** Product appearance and text consistency are preserved more accurately.

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
<summary><strong>Case 6</strong></summary>

**Prompt.** Convert the two men into women. Give the woman on the left a light floral-patterned shirt and the woman on the right a light floral-patterned top, while preserving their poses and interactive expressions and keeping the result natural in a professional office setting.

**Observation.** Gender transformation is successful while pose and interaction remain stable; competing outputs either miss the gender conversion or alter pose.

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
<summary><strong>Case 7</strong></summary>

**Prompt.** Replace the wooden cabinets in the background with white marble.

**Observation.** Only the specified background region is replaced; unrelated background regions remain unchanged.

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
<summary><strong>Case 8</strong></summary>

**Prompt.** Do the following three steps: 1) zoom out to show a seated person facing a laptop; 2) remove all text from the cardboard box; 3) keep the box, laptop, and background unchanged.

**Observation.** The relative position of the box and laptop, as well as the surrounding background, stays fixed as requested.

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
<summary><strong>Case 1</strong></summary>

**Prompt.** Convert this square image into a 3:2 landscape composition.

**Observation.** Resize failure: the model does not successfully perform the requested proportion change from square to 3:2 landscape.

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
<summary><strong>Case 2</strong></summary>

**Prompt.** Convert this portrait image into a landscape one.

**Observation.** Resize failure: converting a portrait-oriented composition into a landscape layout remains unreliable.

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
<summary><strong>Case 3</strong></summary>

**Prompt.** Convert this into a Ghibli-style watercolor animation

**Observation.** Stylization failure: the result does not convincingly reach the requested Ghibli-style watercolor animation target.

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
<summary><strong>Case 4</strong></summary>

**Prompt.** Convert the image into a Miyazaki-style hand-drawn animation.

**Observation.** Stylization failure: the output misses the intended Miyazaki-like hand-drawn aesthetic.

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
