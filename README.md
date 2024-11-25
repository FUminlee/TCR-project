# DePTH2-Analysis

## Overview
DePTH is a predictive model designed to assess the interaction between Human leukocyte antigens(HLA) and T-cell receptor(TCR). By inputting an HLA and a TCR, the model generates a score representing their association. For details on the model structure and usage, please refer to [https://liusi2019.github.io/DePTH-tutorial/](#).

![Description of Image](/Users/fuminli/Desktop/HLA_TCR_clean/figure/overview.png)

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
In our analysis, we primarily use the **Delmonte data** and **TCGA data**. The data provided in the `data` folder has already been preprocessed and is ready for testing. For the raw Delmonte and TCGA data, please refer to  [https://clients.adaptivebiotech.com/pub/delmonte-2023-jaci](#)(Delmonte) and  [https://gdc.cancer.gov/about-data/publications/panimmune](#)(TCGA). Currently, the preprocessing steps are not included in this repository, but we plan to add them in the future.

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

### Confounding Variable Analysis

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



