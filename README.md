# Unofficial Implementation of USAD on WADI and SWaT datasets

This is an unofficial implementation of the USAD architecture modified from the authors' original repo.
Here, it was adapted to work on two datasets, SWaT and WADI, used in the original paper.

Please also refer to the original implementation at https://github.com/manigalati/usad and the paper can be found at https://dl.acm.org/doi/10.1145/3394486.3403392.



## Requirements
This might be a little bit different from what's been specified in the original paper and the author's official repo. (My workstation's GPU supports CUDA 11 instead of CUDA 10, so the torch/cudatoolkit version was adjusted accordingly)
 * python 3.7.11
 * torch 1.9.0
 * cudatoolkit 11.3 (to allow use of GPU, not compulsory)
 * numpy 1.21.2
 * sklearn 1.0.2


## Requesting Access to the Datasets

Both SWaT and WADI datasets are collected by “iTrust, Centre for Research in Cyber Security, Singapore University of Technology and Design”. If you intend to publish paper using these datasets, you have to first request access through their official website https://itrust.sutd.edu.sg/itrust-labs_datasets/ and give explicit credit to their lab.

[SWaT dataset]: https://itrust.sutd.edu.sg/itrust-labs_datasets/dataset_info/#swat
[WADI dataset]: https://itrust.sutd.edu.sg/itrust-labs_datasets/dataset_info/#wadi
