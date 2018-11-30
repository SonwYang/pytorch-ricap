# A PyTorch implementation of RICAP
This repository contains code for a data augmentation method **RICAP (Random Image Cropping And Patching)** based on [Data Augmentation using Random Image Cropping and Patching for Deep CNNs](https://arxiv.org/abs/1811.09030) implemented in PyTorch.

![example](example.png)

## Requirements
- Python 3.6
- PyTorch 0.4

## Training
### CIFAR-10
WideResNet28-10 baseline on CIFAR-10:
```
python train.py --dataset cifar10
```
WideResNet28-10 +RICAP on CIFAR-10:
```
python train.py --dataset cifar10 --ricap True
```
WideResNet28-10 +Random Erasing on CIFAR-10:
```
python train.py --dataset cifar10 --random-erase True
```
WideResNet28-10 +Mixup on CIFAR-10:
```
python train.py --dataset cifar10 --mixup True
```

## Results
| Model                                           |   Error rate (%)  | Loss |
|:------------------------------------------------|:-----------------:|:----:|
| WideResNet28-10 baseline                        |              4.70 | 0.193|
| WideResNet28-10 +RICAP                          |              3.94 | 0.162|
| WideResNet28-10 +Random Erasing                 |              4.36 | 0.163|
| WideResNet28-10 +Mixup                          |              4.09 | 0.232|
| WideResNet28-10 baseline (original paper)       |              3.89 |     -|
| WideResNet28-10 +RICAP (original paper)         |              2.85 |     -|
| WideResNet28-10 +Random Erasing (original paper)|              4.65 |     -|
| WideResNet28-10 +Mixup (original paper)         |              3.02 |     -|

Learning curves of loss and accuracy.

![loss](loss.png)

![acc](acc.png)
