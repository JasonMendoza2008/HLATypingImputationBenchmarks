# HLA Typing Imputation Open Source Benchmarks
Repository containing every inputs and outputs of different HLA typing imputation tools for 
reproducibility purposes when we relied on data that could be shared for these extra tests.

## Data
This repository is aimed at providing a reproducible benchmark for HLA typing imputation tools. The data (n = 1510)
used for this benchmark comes from Nizhny Novgorod, Russia [1] and used as an external testing set on which
none of these tools were trained eliminating the risk of overfitting. The testing data consists of NGS
data from 1510 individuals with high-resolution typings for loci HLA-A, -C, -B, -DRB1, -DQB1. The data does not contain
ambiguities such as the standard non resolved ambiguities like DQB1\*02:01:01G (corresponding to either DQB1\*02:01 or 
DQB1\*02:02 or DQB1\*02:04 or DQB1\*02:06). 

## Structure
In the folder Nizhny_Novgorod_Russia you will find the following files:

- `Russia_2digits.xlsx`, corresponds to the low-resolution data for the 1510 individuals.
- `Russia_4digits.xlsx`, corresponds to the high-resolution data for the 1510 individuals.


And the following folders:

- `HLA-EMMA` with 1/ HLA-EMMA input formatted into what the software accepts, 2/ the raw ouput, and 3/ the Excel file to
compute the tool's performances (`scoresEMMA.xlsx`). For high-resolution conversion, two settings from HLA EMMA were 
tested: EURCAU (European Caucasian) and NL (Netherlands, Leiden).
- `HaploStats` with 1/ HaploStats input formatted into what the software accepts, 2/ the raw ouput of our robot requesting
the website, and 3/ the Excel file to compute the tool's performances. Both the CAU = Caucasian, and EURCAU = European 
Caucasian settings were tested (`scoresCAU.xlsx` and `scoresEURCAU.xlsx`).
- `easyHLA` with 1/ HLA Upgrade inputs formatted into what the software accepts, 2/ the raw ouput, and 3/ the Excel file to
compute the tool's performances (`scores_easyHLA.xlsx`). Inputs are provided as 4 small files because `easyHLA` cannot
process large files. Both the FR = French and EU = European settings were tested.
- `HaploSFHI V2` with 1/ HaploSFHI V2 input formatted into what the software accepts, 2/ the raw ouput, and 3/ the Excel file to
compute the tool's performances (`scoresSFHI.xlsx`). This corresponds to the version online at www.sfhitools.fr/HaploSFHI
and which is described in [2].
- `HaploSFHI V3` with 1/ HaploSFHI V3 input formatted into what the software accepts, and 2/ the Excel file to compute 
the tool's performances (`scoresSFHI5blocks.xlsx`). This version is not online and is the 5-block version of HaploSFHI 
V2. The differences between V2 and V3 are described in [3]. V3 is not available online.
- `HaploDeep` with 1/ HaploDeep input, and 2/ the Excel file to compute the tool's performances 
(`scoresHaploDeep.xlsx`). This is an open-weight ensemble of 5 neural networks. The weights are available on this 
GitHub (in the releases) under the standard ONNX format. There is also MRE code for users that might not be familiar 
with Computer Science.
- `Ensemble` with 1/ the input file, and 2/ the Excel file to compute the tool's performances (`scoresEnsemble.xlsx`).
It uses Majority Voting Ensemble Learning with the tools `HaploSFHI V2`, `HaploSFHI V3`, and `HaploDeep`.

Note that sheets marked as `boostrap` are merely copies of the original sheets without formulas to allow easier 
computations in Python for the confidence intervals of the accuracy metrics.

## References
- [1] Ekaterina Khamaganova. Dataset of HLA NGS typings from individuals of Nizhny Novgorod, Russia, 2020.

## Used in
- [2] Lhotte R, Letort V, Usureau C, Jorge-Cordeiro D, Siemowski J, Gabet L, Cournede P-H, Taupin J-L. Improving HLA typing imputation accuracy and eplet identification with local next-generation sequencing training data. HLA. 2023;1‐14. https://doi.org/10.1111/tan.15222
- [3] Lhotte R, Benbekrite C, Daubonne X, Cappia C, Usureau C, Letort V, Taupin J-L. HaploDeep.
