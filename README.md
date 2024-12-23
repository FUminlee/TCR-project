# DePTH2-Analysis

## Overview
DePTH is a predictive model designed to assess the interaction between Human leukocyte antigens(HLA) and T-cell receptor(TCR). By inputting an HLA and a TCR, the model generates a score representing their association. For details on the model structure and usage, please refer to [https://liusi2019.github.io/DePTH-tutorial/](https://liusi2019.github.io/DePTH-tutorial/). This GitHub repository provides an analysis of several significant confounding factors involved in the DePTH model, along with improvements to the original model, resulting in DePTH 2.0. All code in this repository follows the methodology described in the paper: [Improved Deep Learning Prediction of TCR-HLA Associations](https://www.biorxiv.org/content/10.1101/2024.11.22.624910v1).

## Features
This repository focuses on the further development and analysis of the DePTH model, including:
1. **Confounding Factors Analysis**  
   - Analysis of factors such as:
     - TCR Generation Probability
     - CDR3 Length  

2. **DePTH 2.0 Enhancements**  
   - Updates and improvements to the original DePTH model for better performance and usability.


## Getting Started

### Data Availability
In our analysis, we primarily use the **Delmonte data** and **TCGA data**. The data provided in the `data` folder has already been preprocessed and is ready for testing. For the raw Delmonte and TCGA data, please refer to  [(Delmonte)](https://clients.adaptivebiotech.com/pub/delmonte-2023-jaci) and  [(TCGA)](https://gdc.cancer.gov/about-data/publications/panimmune). Currently, the preprocessing steps are not included in this repository, but we plan to add them in the future. The preprocessed data provides the HLA-TCR pairs in the Positive Set and Negative Set. For details on the selection criteria, please refer to the supplementary materials of [Improved Deep Learning Prediction of TCR-HLA Associations](https://www.biorxiv.org/content/10.1101/2024.11.22.624910v1).

### Prerequisites
All the analyses conducted in this project are implemented in **R**. Depending on the type of analysis, different R packages are required. For convenience, we list all the required packages below. Please ensure they are installed before running the scripts.

### Required R Packages
To run the analyses, you will need the following R packages:

- `tidyr`
- `dplyr`
- `lmtest`
- `stringr`
- `ggplot2`
- `gridExtra`
- `plotly`
- `Matrix`
- `uwot`
- `irlba`
- `pROC`
- `ggpointdensity`
- `viridis`
- `purrr`
- `igraph`
- `pbapply`
- `data.table`
- `Rtsne`
- `leidenbase`
- `reshape2`

### Installing Required Packages
You can install the required packages in R using the following command:

```R
required_packages <- c(
  "tidyr", "dplyr", "lmtest", "stringr", "ggplot2", "gridExtra", "plotly",
  "Matrix", "uwot", "irlba", "pROC", "ggpointdensity", "viridis", "purrr",
  "igraph", "pbapply", "data.table", "Rtsne", "leidenbase", "reshape2"
)

install.packages(setdiff(required_packages, installed.packages()[, "Package"]))
```

### Confounding Factors Analysis

#### TCR Generation Probability

The analysis of TCR generation probability focuses on understanding the relationship between TCR generation probability and the scores generated by the DePTH model. This is further divided into two main aspects:

1. Investigating the relationship between TCR generation probability and the DePTH mean score (the average score between a given TCR and all HLAs).  
2. Exploring whether TCR generation probability alone provides valuable insights into the association between HLA and TCR.  

This analysis helps to assess the extent to which TCR generation probability influences or correlates with DePTH model predictions.

#### CDR3 Length

The analysis of CDR3 length focuses on understanding its relationship with the scores provided by the DePTH model. This is divided into three main aspects:

1. Examining the distribution of CDR3 length in the **Positive Set** and **Negative Set**.  
2. Exploring the relationship between CDR3 length and the DePTH mean score (the average score between a given TCR and all HLAs).  

This analysis helps to assess the extent to which CDR3 Length influences or correlates with DePTH model predictions.

Additionally, other analyses and validations mentioned in the paper can be found in the corresponding files within the `analysis` folder. To run these analyses:
1. Download the `data` folder.  
2. Update the `data` directory paths in the `analysis` scripts.  
3. Execute the scripts to reproduce the results.

