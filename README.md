# app-map-atlas

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Maps a retinotopic or cortical atlas (Benson14, Wang15, Glasser16 or Rosenke18) onto a FreeSurfer subject with neuropythy and outputs a volumetric parcellation, atlas maps and surface data.**

Runs python -m neuropythy atlas on the FreeSurfer subject, converts the resulting volumes to NIfTI with FreeSurfer mri_convert and attaches a label.json for the chosen atlas. Use it to get visual-area or multimodal cortical labels in subject space without functional data. Requires a FreeSurfer license.

| | |
|---|---|
| 📥 **Inputs** | `neuro/freesurfer` · `neuro/anat/t1w` (optional) |
| 📤 **Outputs** | `neuro/parcellation/volume` · `neuro/maps` · `neuro/surface/vertices` |
| 🐳 **Container** | `brainlife/dipy:1.4.1` |
| ⚙️ **Resources** | 2 CPUs · 20 GB memory · 4 h walltime |
| 🔑 **Requires** | `FREESURFER_LICENSE` |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.922](https://doi.org/10.25663/brainlife.app.922) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `freesurfer` | `neuro/freesurfer` | yes | FreeSurfer subject directory. |
| `reference` | `neuro/anat/t1w` | no | Optional T1w reference image. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `parcellation` | `neuro/parcellation/volume` | Atlas labels as a volumetric parcellation with label.json. |
| `volumes` | `neuro/maps` | Atlas maps (e.g. eccentricity, polar angle for Benson14) as volumes. |
| `surfaces` | `neuro/surface/vertices` | Atlas data on the subject's surface vertices. |

<details>
<summary><b>⚙️ Parameters</b> (1)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `atlas` | enum | `benson14` | Atlas to map: benson14, wang15, glasser16 or rosenke18. Options: `wang15`, `glasser16`, `rosenke18`, `benson14`. |

</details>

<!-- brainlife-app:end -->

