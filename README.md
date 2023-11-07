# Trajectory-based Global Sensitivity Analysis in Multiscale Models

## Table of contents

**Adapt in the end accordingly**

- [Overview](#overview)
- [Methodology](#methodology)
- [Repository Contents](#repository-contents)
- [Data](#data)
- [Getting Started](#getting-started)
- [Development](#development)
- [References](#references)

## Overview
This Git repository offers the code for implementing the concepts presented in the "Trajectory-based Global Sensitivity Analysis in Multiscale Models" paper. The paper introduces a new method for conducting global sensitivity analysis (GSA), tailored to accommodate the unique features of agent-based models (ABMs) used in modeling complex systems, which include diverse temporal dynamics and multi-level characteristics. The proposed framework employs Grassmannian diffusion maps (GDMaps) and sparse polynomial chaos expansion (PCE) to reduce data dimensionality and compute sensitivity indices for uncertain input parameters. The method is applied to three models: a classic Lotka-Volterra dynamical system, DeepABM-COVID, and a poverty trap formation ABM. 

## Methodology

<p align="center">
  <img width="1000" src="repository_files/GSA_GDMaps_PCE_pipeline.jpg">
</p>

## Repository Contents

- `GDMaps_PCE`: This directory holds the source code for the newly introduced method of GSA using GDMaps PCE.
- `notebooks`: Within this folder, you'll find various illustrative examples demonstrating the method's practical application. It includes the following files:
  - `data`: Contains the datasets used for generating plots.
  - `plots`: Stores all the plots featured in both the main text and Supplementary Information (SI).
  - `pce_accuracy`: Stores the resulting plots produced during the assessment of the accuracy of the PCE step.
  - `DeepABM_GSA.ipynb`: A Jupyter notebook illustrating the framework's use on the DeepABM COVID-19 model.
  - `DeepABM_SobolGSA.ipynb`: Another Jupyter notebook showcasing GSA for the DeepABM COVID-19 model using traditional Sobol' index calculation methods across multiple time steps.
  - `LV_GSA.ipynb`: A Jupyter notebook providing insight into the framework's application on the Lotka-Volterra (LV) model.
  - `PT-6_GSA.ipynb`:  A Jupyter notebook demonstrating the application of the framework on the poverty trap formation ABM at multiple analysis levels: micro, meso, and macro.
- `Snellius_DeepABM`: This is not a standalone repository; rather, it contains files used to compile data for the DeepABM COVID-19 model, in collaboration with the [deepabm-covid](https://github.com/ayushchopra96/deepabm-covid.) repository.

## Data

To use the original data for DeepABM-COVID, obtain it from [https://figshare.com/articles/dataset/data_zip/23515965](https://figshare.com/articles/dataset/output_data_zip/22216921) and insert the unzipped folder named 'output_data' into the 'notebooks/data/data_DeepABM' directory. You can find the code for writing datafiles from the original data in the 'DeepABM_SobolGSA.ipynb' file located in the 'notebook' directory.

For the poverty trap formation ABM, dowload the data from [https://figshare.com/articles/dataset/ABM_output/24517021](https://figshare.com/articles/dataset/ABM_output/24517021). To run with it, add the unzipped folder into the `notebooks/data/data_PT` folder, and rename it to `arrays_for_GDMaps`.

## Getting Started

1. Clone the repository:
```
git clone git@github.com:bazvalya/Rethinking_GSA.git
```
and navigate to it on the local machine:
```
cd Rethinking_GSA
```
2. Create a virtual environment (Python 3.10):
```
python3.10 -m venv new_environment_name
```
and activate it with:
```
source new_environment_name/bin/activate
```
3. Install the required packages with:
```
pip install -r requirements.txt
```

## Development

We are continuously working on the enhancement of this repository. Our aim is to provide aa collection of reusable code that empowers researchers to effortlessly replicate our results and utilize our framework for conducting GSA. Whether you intend to recreate our results or embark on new research endeavors, this repository equips you with the essential tools and resources to facilitate your pursuits.

## References 

The repository containing the source code for the poverty trap formation ABM can be found at [charlesaugdupont/poverty-trap](https://github.com/charlesaugdupont/poverty-trap).

A significant portion of our implementation is derived from [GDM-PCE](https://github.com/katiana22/GDM-PCE). We want to extend our appreciation to the contributors of the original repository for their invaluable contributions.
