# Unofficial Implementation of USAD on WADI and SWaT datasets

This is an unofficial implementation of the USAD architecture modified from the authors' original repo.
Here, it was adapted to work on two datasets, SWaT and WADI, used in the original paper.

Please also refer to the original implementation at https://github.com/manigalati/usad and the paper https://dl.acm.org/doi/10.1145/3394486.3403392.



## Requirements
This might be a little bit different from what's been specified in the original paper and the author's official repo. (My workstation's GPU supports CUDA 11 instead of CUDA 10, so the torch/cudatoolkit version was adjusted accordingly)
 * python 3.7.11
 * torch 1.9.0
 * cudatoolkit 11.3
 * numpy 1.21.2
 * sklearn 1.0.2
 * pandas 1.3.5
 * matplotlib 3.5.1


## Requesting Access to the Datasets and Usage

Both SWaT and WADI datasets are collected by “iTrust, Centre for Research in Cyber Security, Singapore University of Technology and Design”. If you intend to publish paper using these datasets, you have to first request access through their official website https://itrust.sutd.edu.sg/itrust-labs_datasets/ and give explicit credit to their lab.

[SWaT dataset]: https://itrust.sutd.edu.sg/itrust-labs_datasets/dataset_info/#swat
[WADI dataset]: https://itrust.sutd.edu.sg/itrust-labs_datasets/dataset_info/#wadi

### Dataset Usage
The data files are too large to be uploaded to the repo. After your access to the datasets has been approved, you should create a folder "input" under the main branch, then download the corresponding CSV files into it. (What I was using when testing was the Attack_v0 and Normal_v1 under "SWaT A1&A2 Dec 2015 - Physical", and the data files within "WADI A1_9 Oct 2017")

### Some Issues with the WADI datasets 
The WADI datasets contains a lot of missing values (will be interpreted by NaN if imported into pd.Dataframe). These NaNs will affect the training of the model (so you would get NaN loss for every epoch). 
My solution here for now is to remove the columns that doesn't have any valid entries and replace the rest NaNs with zeros. (But there might be a better way, so open to discussions I guess)
