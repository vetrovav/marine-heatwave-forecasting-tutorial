# [Graph Neural Networks for Ocean Forecasting: Predicting Sea Surface Temperature Anomalies and Marine Heatwave Precursors]

![Python](https://img.shields.io/badge/Python-3.13.15-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-2.11.0-EE4C2C?logo=pytorch&logoColor=white)
![PyTorch Geometric](https://img.shields.io/badge/PyTorch_Geometric-2.8.1-3C2179)
![Xarray](https://img.shields.io/badge/Xarray-2025.12.0-336699)
![License](https://img.shields.io/badge/License-MIT-green)

## Abstract
The variability of sea surface temperature is one of the most consequential signals in the climate system: it shapes weather patterns, drives ENSO, and produces marine heatwaves (MHWs), prolonged extreme warm events that devastate marine ecosystems and the industries that depend on them.

Most deep learning approaches to SST forecasting treat the ocean as an image and apply convolutional architectures. But the ocean is not an image: distant regions are physically and statistically coupled through teleconnections: an anomaly in the equatorial Pacific is linked to conditions off Australia, in the Indian Ocean, and beyond. A graph structure can allow to incorporate those long-range dependencies directly into the model.

In this tutorial we build that idea end-to-end: convert a global gridded SST product into a graph whose edges encode teleconnections, train a GraphSAGE model for 1-month-ahead global SSTA forecasts, evaluate it against persistence and climatology baselines, map where the GNN adds skill (including known MHW hotspots), and extend forecasts to longer leads recursively. Throughout, we work with the paper's published artifacts: archived forecasts, model checkpoints, and code. Thefore users can compare everything they build against the published results
### Authors:

Provide a bulleted list of all author names, affiliations, and contact links.
- **[author 1 fullname]**, [Affiliation/Institution] , [contact email]
- **[author 2 fullname]**, [Affiliation/Institution] , [contact email]

> Reminder for Round II reviews please keep all tutorial materials anonymized to support the double-blind review process.

Originally presented at the [insert CCAI event or workshop full name with the year].
## Learning Objectives
After completing this tutorial, participants should be able to:
1. [Learning objective]
2. [Learning objective]
3. [Learning Objective]

### Intended Audience
[Describe the intended audience and please be as specific as possible, especially with respect to their expected background.]

### Prerequisites
Participants should be familiar with:
- [Prerequisite]
- [Prerequisite]
- [Prerequisite]

### Tutorial walkthrough video

 
➡️ [**Video URL**](url)
**Duration:** [XX minutes]


---

## Repository Contents
 
| Resource | Description |
|----------|-------------|
| `notebook/` | Jupyter notebook |
| `model-card/` | Model documentation (if applicable)|
| `datasheet/` | Dataset documentation (if applicable)|
| `emissions-reporting/` | Energy/carbon reporting |
| `figures/` | Images and figures (optional) |
| `data/` | Dataset sample (optional) |

---

## Software Requirements
 
**Primary language:** [Python / R / Julia / Other]
 
**Language version:** [e.g., Python 3.12]
 
### Major Packages
- [package] [version]
- [package] [version]
- [package] [version]
 

See `requirements.txt` for the complete environment.

---

## Access this tutorial
We recommend executing this notebook in a Colab environment to gain access to GPUs and to manage all necessary dependencies. <a target="_blank" href="yourcolabnotebooklinkenabledwithpropershareconditions">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

To run locally, see:

➡️ `notebook/[final_notebook_name_without_version.ipynb]`

**Estimated time to execute end-to-end:** [insert runtime here].

**Last successfully tested:** [YYYY-MM-DD]

### Model Information
This submission [does/does not] involve a machine-learning model.

[If the tutorial trains, fine-tunes, adapts, evaluates, or demonstrates an AI/ML model please provide a model-card. A description of model-cards is provided [here](https://arxiv.org/abs/1810.03993).]

If applicable, see:

➡️ `model-card/MODEL_CARD.md`

### Dataset Information
This submission [does/does not] use a dataset.

[If the tutorial utilizes a dataset, please provide a datasheet. A description of datasheets is provided [here](https://arxiv.org/abs/1803.09010).]

If applicable, see:

➡️ `datasheet/DATASHEET.md`

### Sustainbility/Carbon Emissions
Carbon emissions associated with the computational experiments were measured using [CodeCarbon or emissions tracking tool of choice].
 
For more details, go to:

 
➡️ `emissions-reporting/CARBON_EMISSIONS.md`


---

## Contribute to this tutorial

Please refer to these [GitHub instructions](https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project#about-forking) to open a pull request via the "fork and pull request" workflow. 

Pull requests will be reviewed by members of the Climate Change AI Tutorials team for relevance, accuracy, and conciseness.

## Climate Change AI Tutorials
Check out the [tutorials page](https://www.climatechange.ai/tutorials?) on our website for a full list of tutorials demonstrating how AI can be used to tackle problems related to climate change.

## License
Usage of this tutorial is subject to the MIT License.

## Cite

### Plain Text
[Insert plain text citation of accepted submission here.]

### BibTeX
[Insert BibTex citation of accepted submission here.]
