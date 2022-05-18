## Hybrid Classical-Quantum Deep Learning (HCQDL)
[Project]() | [Arxiv](https://arxiv.org/pdf/1905.01164.pdf) | [CVF]() 
### Official tensorflow implementation of the paper: "Semiconductor Defect Detection by Hybrid Classical-Quantum Deep Learning"
####  CVPR 2022


## HCQDL's Architecture.
* HCQDL uses quantum circuits to nonlinearly transform classical inputs into features that can then be used in a number of deep learning algorithms. HCQDL consists of classical layer, quantum layer, and fully connection layer. Please refer to ```Hybrid_CNN.py```
<img style="float: left;" src="./images/1.png" width="70%">

### Classical Layer (SP&A-Net)
* The first function of SP&A-Net is the self-proliferation, using a series of linear transformations to generate more feature maps at a cheaper cost. We can train image classifier in a more efficient way. Please refer to ```Self_Proliferate.py```
<img style="float: left;" src="./images/SP.png" width="70%">


* The second function is self-attention, capturing the long-range dependencies of the feature map using the channel-wise and spatial attention mechanism.

## Code

### Install dependencies

```
python -m pip install -r requirements.txt
```

This code was tested with python 3.7  

###  Train
This script is based on CIFAR-10 as an example. For training, please run:

```
python TestRun.py
```

## Script Introduction

```Self_Proliferate.py``` is used to generate more feature maps (As paper section 3.1).

```Self_Attention.py``` is used to capturing the long-range dependencies of the feature map (As paper secton 3.2).

```Self_Proliferate_and_Attention.py``` follow the spirit of MobileNet,  "capture features in high dimensions and transfer information in low dimensions",  to make the network more efficient. (As paper secton 3.3).

```SPA_Net.py``` is the overall network architecture of SP&A-Net. Please refer section 3.4 of this paper.

```SP&A-Net-Test-Run.ipynb``` is in the form of a Jupyter Notebook as a simple display with CIFAR-10 as the training object.

