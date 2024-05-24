# IMF PRGT Funding Classifier

## Table of Contents
1. [Introduction](#introduction)
2. [Team Members](#team-members)
3. [Motivation](#motivation)
4. [Data Description](#data-description)
    - [Data Sources](#data-sources)
    - [Variables](#variables)
5. [Data Collection and Cleaning](#data-collection-and-cleaning)
    - [Data Collection](#data-collection)
    - [Data Cleaning](#data-cleaning)
6. [Analytics Models](#analytics-models)
    - [Logistic Regression](#logistic-regression)
    - [Linear Discriminant Analysis (LDA)](#linear-discriminant-analysis-lda)
    - [CART (Classification and Regression Trees)](#cart-classification-and-regression-trees)
    - [Random Forest](#random-forest)
    - [Vanilla Bagging](#vanilla-bagging)
    - [Boosting](#boosting)
    - [Neural Networks](#neural-networks)
7. [Results Summary](#results-summary)
8. [Impact](#impact)
9. [Conclusion](#conclusion)
10. [References](#references)
11. [Contact](#contact)

## Introduction

This project focuses on building a model to predict if a country should be approved for receiving concessional loans from the International Monetary Fund (IMF) under the Poverty Reduction and Growth Trust (PRGT) program. The PRGT program provides zero-interest loans to low-income countries, and our model aims to streamline the process by accurately predicting loan eligibility, thereby saving time and resources.

## Team Members

- Yifan Yang
- April Zhang
- Jessica Guo
- Ruiyi Ji
- Yiyao Jiang

## Motivation

The IMF provides concessional loans to low-income countries, a process that can be time-consuming due to the numerous factors involved. Our model seeks to assist in this process by predicting loan approval eligibility with high accuracy, thus saving the IMF time and money in reviewing applications.

## Data Description

### Data Sources
- **MONA Database**: Contains various types of arrangements, not all relevant to the PRGT program.
- **IMF Financial Data Query Tool**: Contains "Flows" and "Commitments" data. "Flows" data was chosen for this project.

### Variables
We selected the following variables as our independent variables based on their relevance to the PRGT criteria:
- **Real GDP Growth (Annual percent change)**
- **Food Supply (kcal/capita/day)**
- **Number of Natural Disasters**
- **Total PRG Credit Outstanding**
- **Current Account Balance**
- **Capital Account Balance**
- **Financial Account Balance**
- **Reserves**

## Data Collection and Cleaning

### Data Collection
We used the IMF Financial Data Query Tool to collect data on various economic indicators and PRGT loan flows. The data was then filtered to include relevant variables for our analysis.

### Data Cleaning
- Grouped data by country and year.
- Converted "Flows" data to an indicator variable.
- Ensured consistency in country names and merged datasets.
- Replaced missing values with 0s for natural disasters and total PRG credit outstanding.
- Dropped other missing values and converted strings to numeric values where necessary.

## Analytics Models

We built several models to perform binary classification, predicting whether a country should receive PRGT funding:

### Logistic Regression
- **Accuracy**: 0.6656
- **True Positive Rate (TPR)**: 0.4008
- **False Positive Rate (FPR)**: 0.1787

### Linear Discriminant Analysis (LDA)
- **Accuracy**: 0.6516
- **True Positive Rate (TPR)**: 0.3924
- **False Positive Rate (FPR)**: 0.1960

### CART (Classification and Regression Trees)
- **Accuracy**: 0.6438
- **True Positive Rate (TPR)**: 0.6498
- **False Positive Rate (FPR)**: 0.3598

### Random Forest
- **Accuracy**: 0.6688
- **True Positive Rate (TPR)**: 0.6540
- **False Positive Rate (FPR)**: 0.3226

### Vanilla Bagging
- **Accuracy**: 0.6219
- **True Positive Rate (TPR)**: 0.6540
- **False Positive Rate (FPR)**: 0.3970

### Boosting
- **Accuracy**: 0.6750
- **True Positive Rate (TPR)**: 0.6456
- **False Positive Rate (FPR)**: 0.3077

### Neural Networks
- **Accuracy**: 0.6969
- **True Positive Rate (TPR)**: 0.5907
- **False Positive Rate (FPR)**: 0.2407

## Results Summary

| Model                | Accuracy | TPR    | FPR    |
|----------------------|----------|--------|--------|
| Logistic Regression  | 0.6656   | 0.4008 | 0.1787 |
| Linear Discriminant Analysis (LDA) | 0.6516 | 0.3924 | 0.1960 |
| CART                 | 0.6438   | 0.6498 | 0.3598 |
| Random Forest        | 0.6688   | 0.6540 | 0.3226 |
| Vanilla Bagging      | 0.6219   | 0.6540 | 0.3970 |
| Boosting             | 0.6750   | 0.6456 | 0.3077 |
| Neural Networks      | 0.6969   | 0.5907 | 0.2407 |

## Impact

Our model can be applied to the IMF's reviewing process for the PRGT program as an initial screening tool to identify countries that should be reviewed in more detail. Although the model's accuracy is not perfect, it provides a valuable starting point that can be refined with additional data and improved techniques.

## Conclusion

Based on the performance of our models, we recommend using the Boosting model due to its balanced accuracy and TPR. However, ethical considerations must be taken into account, as model biases could impact decision-making. Future work should focus on gathering more comprehensive data and addressing ethical issues to enhance the model's reliability and fairness.

## References

- [IMF Support for Low-Income Countries](https://www.imf.org/en/About/Factsheets/IMF-Support-for-Low-Income-Countries)
- [IMF Financial Data Query Tool](https://www.imf.org/external/np/fin/tad/query.aspx)
- [FAO Food Supply Data](https://www.fao.org/faostat/en/#data/FBSH)
- [EM-DAT Natural Disasters Database](https://public.emdat.be/)
- [IMF World Economic Outlook](https://www.imf.org/external/datamapper/NGDP_RPCH@WEO/OEMDC/ADVEC/WEOWORLD)
