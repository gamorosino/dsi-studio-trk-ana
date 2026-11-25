<h1 align="center">dsi-studio-trk-ana</h1>

<p align="center">
  Computes tract shape and size measures (length, span, volume, diameter, surface area, curl, elongation, irregularity) from a DSI Studio tinytrack file with DSI Studio and outputs a TSV table.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.842"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.842-blue.svg" alt="Run on brainlife.io"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Computes tract shape and size measures (length, span, volume, diameter, surface area, curl, elongation, irregularity) from a DSI Studio tinytrack file with DSI Studio and outputs a TSV table.**

Runs dsi_studio --action=ana --export=stat on the tract file and stores the statistics as tractmeasure.tsv. Use it to quantify tract shape after tractography or bundle recognition in DSI Studio.

| | |
|---|---|
| **Inputs** | `neuro/dsistudio/tinytrack` |
| **Outputs** | `neuro/dsistudio/tractmeasures` |
| **Container** | `dsistudio/dsistudio:hou-2024-12-26` |
| **Resources** | 1 CPUs |
| **Run it** | [doi.org/10.25663/brainlife.app.842](https://doi.org/10.25663/brainlife.app.842) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `track` | `neuro/dsistudio/tinytrack` | yes | Tract file in DSI Studio tinytrack (.tt.gz) format. |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `stats` | `neuro/dsistudio/tractmeasures` | Table of tract measures (tractmeasure.tsv). |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.842](https://doi.org/10.25663/brainlife.app.842), choose `neuro/dsistudio/tinytrack` from your project and press **Execute**. The results are saved to your project as `neuro/dsistudio/tractmeasures`.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) (the App runs in `dsistudio/dsistudio:hou-2024-12-26`), [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "tt": "/path/to/track/tt"
   }
   ```

3. Run `./main`.

## Troubleshooting

- **ERROR: Source or tract file does not exist. Check paths in config.json.**: Provide a tinytrack input.
- **ERROR: Output file not generated. Check DSI Studio logs.**: Check the DSI Studio log for errors reading the tract file.

## Features

This app computes detailed tract properties, including:
- **Length**
- **Span**
- **Volume**
- **Diameter**
- **Surface Area**
- **Curl**
- **Elongation**
- **Irregularity**

The results are exported as structured statistics for further analysis.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- dsi-studio-trk-ana. brainlife.io App. [doi:10.25663/brainlife.app.842](https://doi.org/10.25663/brainlife.app.842)
- Yeh FC. Shape analysis of the human association pathways. NeuroImage 223:117329 (2020). [doi:10.1016/j.neuroimage.2020.117329](https://doi.org/10.1016/j.neuroimage.2020.117329)
- DSI Studio function:
- Brainlife.io:
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

Gabriele Amorosino
