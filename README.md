# Neural Network From Scratch

## Overview

This project is a personal learning exercise to understand how Neural Networks and Convolutional Neural Networks (CNNs) work under the hood—without relying on high-level libraries like PyTorch. Everything is implemented from scratch using only NumPy.

## Neural Network

### Implementation

- ReLU is used as the activation function, and Mean Squared Error (MSE) is used as the loss function—both with their respective derivatives.
- A `NeuralNetwork` class is implemented, which supports:
  - Custom `input_shape`, `hidden_units`, and `output_shape`
  - Multiple fully connected layers
  - Forward and backward propagation

### Results

| Task                            | Implementation | Loss   |
| ------------------------------- | -------------- | ------ |
| Linear Regression (Small Range) | Custom (NumPy) | 0.0007 |
|                                 | PyTorch        | 0.0024 |
| Linear Regression (Large Range) | Custom (NumPy) | 0.0033 |
|                                 | PyTorch        | 0.0055 |
| Moon Dataset Classification     | Custom (NumPy) | 0.0006 |
|                                 | PyTorch        | 0.0300 |

## Convolutional Neural Network

### Implementation

- Fully connected layers are reused from the neural network implementation.
- A Softmax activation with cross-entropy loss is added for classification.
- The CNN starts simple: a single-layer, single-kernel design without padding or pooling.
- Features are gradually added:
  - Padding
  - Max pooling
  - Multiple kernels
  - Multiple layers
- Forward and backward propagation are implemented for each configuration.

### Results

| CNN Configuration                                               | Loss   | Accuracy |
| --------------------------------------------------------------- | ------ | -------- |
| Single layer, single kernel, no padding, no pooling             | 0.3248 | 86.60%   |
| Single layer, single kernel, no padding, with max pooling       | 0.3942 | 84.22%   |
| Single layer, single kernel, with padding and max pooling       | 0.3427 | 85.93%   |
| Single layer, multiple kernels, with padding and max pooling    | 0.3091 | 86.13%   |
| Multiple layers, multiple kernels, with padding and max pooling | 0.5353 | 79.30%   |
