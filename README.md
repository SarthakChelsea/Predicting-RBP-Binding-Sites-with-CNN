# RBP Binding Site Prediction using CNN

## Table of Contents
1. [Introduction](#introduction)
2. [Background](#background)
3. [Dataset](#dataset)
4. [Model Architecture](#model-architecture)
5. [Results](#results)
6. [Conclusion](#conclusion)

## Introduction

This project aims to predict RNA-binding protein (RBP) binding sites using a Convolutional Neural Network (CNN). The model is designed to analyze RNA sequences and predict whether specific sites are likely to bind with the AGO2 protein, a key player in the RNA-induced silencing complex (RISC).

## Background

### RNA-Binding Proteins (RBPs)

RNA-binding proteins (RBPs) are crucial in post-transcriptional regulation of gene expression. They interact with RNA molecules to influence various processes such as RNA splicing, stability, localization, and translation. Identifying RBP binding sites is essential for understanding these regulatory mechanisms.

### AGO2 Protein

In this project, we focus on the AGO2 protein, a key component of the RISC complex. AGO2 is involved in RNA silencing processes, including microRNA-mediated gene regulation. Predicting AGO2 binding sites can provide insights into potential microRNA target sites and gene regulation mechanisms.

## Dataset

The dataset consists of RNA sequences labeled as positive (binding) or negative (non-binding) for AGO2. The data is processed into a format suitable for CNN input, with each nucleotide represented using one-hot encoding.

- Training set: 29,686 sequences
- Test set: 1,000 sequences
- Sequence length: 507 nucleotides

## Model Architecture

The CNN model architecture is as follows:

1. Input layer: Accepts RNA sequences (507x1x4)
2. Convolutional layers:
   - Conv1: 128 filters, kernel size (10,1)
   - Conv2: 128 filters, kernel size (10,1)
   - Conv3: 256 filters, kernel size (5,1)
3. Max pooling layers after Conv1 and Conv2
4. Global average pooling after Conv3
5. Fully connected layers:
   - FC1: 256 to 128 units
   - FC2: 128 to 1 unit (output)
6. Dropout layers for regularization

The model uses ReLU activation for hidden layers and sigmoid activation for the output layer.

## Results

The current model shows limited learning, with the loss decreasing only slightly over 5 epochs:
Epoch 1/10, Train Loss: 0.6914, Val Loss: 0.6929
Epoch 2/10, Train Loss: 0.6911, Val Loss: 0.6929
Epoch 3/10, Train Loss: 0.6911, Val Loss: 0.6929
Epoch 4/10, Train Loss: 0.6908, Val Loss: 0.6929
Epoch 5/10, Train Loss: 0.6908, Val Loss: 0.6930
Early stopping triggered

## Conclusion

This project demonstrates an initial attempt at predicting RNA-binding protein (RBP) binding sites using a Convolutional Neural Network (CNN). While the model architecture and dataset preparation were carefully designed, the current results indicate limited success in model training, with only slight improvements in loss over several epochs. This suggests that the model may require further optimization, such as adjusting hyperparameters, exploring alternative architectures, or incorporating more advanced techniques like attention mechanisms. Future work will focus on addressing these challenges to improve the model's ability to accurately predict RBP binding sites.
