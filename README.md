# FIAML-LR
FIAML-LR corresponds to the code framework of the meta-learning part of the paper. 
Due to the large dataset and the ease of finding the corresponding open source on the Internet, it is not released here

## Requirements

- Ubuntu 18.04
- Anaconda3
- Python==3.7.12
- PyTorch==1.7.1
- numpy==1.21.5
- sklearn==1.0.2

To install requirements, first download Anaconda3 and then run the following:

```setup
bash install.sh
```

## Hardware Requirements
- GPU with memory more than 27GB for a single-GPU ResNet12 backbone second-order training.

## Datasets
For miniIamgenet, the dataset can be downloaded from the link provided from MAML++ public code.
make a directory named 'datasets' and place the downloaded miniImagnet under the 'datasets' directory.
rename the unzip miniImagnet dataset as mini_imagenet_full_size.

## Training

To train the model(s) in the paper, run this command in experiment_scripts folder:

For single GPU
```train
bash fiaml-lr+maml.sh 0
```
where 0 represent GPU_ID.

For multi-GPU,

```train
bash fiaml-lr+maml.sh 0 1 2 3
```
where 0 1 2 3 represent 4 GPU_IDs.


## Evaluation

After training is finished, the same command is run to evaluate:

For single GPU:
```eval
bash fiaml-lr+maml.sh 0
```
For multi-GPU:
```eval
bash fiaml-lr+maml.sh 0 1 2 3
```
where 0 1 2 3 represent 4 GPU_IDs.

## Warning 
Multiple GPUs for training may result in inflated accuracy, please use with caution.
