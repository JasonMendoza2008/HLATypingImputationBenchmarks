# HLA Typing Imputation Open Source Benchmarks
Repository containing every inputs and outputs of different HLA typing imputation tools' for 
reproducibility purposes when we relied on data that could be shared for these extra tests.

## Data
This repository is aimed at providing a reproducible benchmark for HLA typing imputation tools. The data
used for this benchmark comes from Nizhny Novgorod, Russia [1] and used as an external testing set on which
none of these tools were trained eliminating the risk of overtting (n = 1510). The testing data consists of NGS
data from 1510 individuals with high-resolution typings for loci HLA-A, -C, -B, -DRB1, -DQB1. The data does not contain
ambiguities such as the standard non resolved ambiguities like DQB1*02:01:01G (corresponding to either DQB1*02:01 or 
DQB1*02:02 or DQB1*02:04 or DQB1*02:06). 

## Structure
In the folder Nizhny_Novgorod_Russia you will find the following files:
- `Russia_2digits.xlsx`, corresponds to the low-resolution data for the 1510 individuals
- `Russia_4digits.xlsx`, corresponds to the high-resolution data for the 1510 individuals
And the following folders:
- `HLA-EMMA` with HLA-EMMA input formatted into what the software accepts, the raw ouput and the Excel file to
compute the tool's performances (`scoresEMMA.xlsx`).
- `HaploStats` with HaploStats input formatted into what the software accepts, the raw ouput of our robot requesting
the website and the Excel file to compute the tool's performances (`scoresCAU.xlsx` and `scoresEURCAU.xlsx`).
- `HaploSFHI` with HaploSFHI input formatted into what the software accepts, the raw ouput and the Excel file to
compute the tool's performances (`scoresSFHI.xlsx`).
- `easyHLA` with HLA Upgrade inputs formatted into what the software accepts, the raw ouput and the Excel file to
compute the tool's performances (`scores_easyHLA.xlsx`).

## References
[1] Ekaterina Khamaganova. Dataset of HLA NGS typings from individuals of Nizhny Novgorod, Russia, 2020.
