[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/Aoc8-XSk)
## P1. CIFAR10 CNN: training using minibatch gradient descent algorithms

Implement a CNN architecture that consists of 3 convolutional layers followed by a fully connected layer of 1000 units. 

Each convolutional layer consists of a sublayer of 5x5 convolutional filters with stride 1 followed by a sublayer of 2x2 max-pool units with stride 2. Each neuron applies ReLU activation function.

**Task:** Evaluate and plot **the average training loss per epoch** versus the number of epoches for the training dataset, for the following optimization algorithms:
- Mini-batch gradient descent
- Mini-batch AdaGrad
- Mini-batch RMSProp
- Mini-batch gradient descent with Nesterov’s momentum
- Mini-batch Adam 

In addition, show the results by adding dropout. Comment the results. 

**Hints:**

- Load CIFAR10 data by the following code:
```
from keras.datasets import cifar10
(data_train, label_train), (data_test, label_test) = cifar10.load_data()
```
- In order to reduce the training time, use only the first 50 mini-batches for each epoch. 
- More specifically, at the beginning of each epoch, randomly shuffle the whole dataset training dataset. Then, only iterate through the first 50 mini-batches for one epoch training.  
- Training on Google Colab GPU is highly recommended. The training time on 1 GPU is roughly 1 minute per epoch.  

The hyper-parameter settings:
- minibatch size = 128 
- learning rate = 0.001
- total number of epoches = 100

## P2. CIFAR10 image classification

Design and implement a convolutional neural network for the CIFAR10 image classification task aiming to achieve a high test accuracy. Evaluate the classification accuracy by reporting top-1 and top-5 test error rates. 

**Task:** Plot the average loss, top-1 error rate and top-5 error rate per epoch versus the number of epochs for the training and the test dataset. Make sure to well describe and justify your network architecture design choices. You must report results for at most three combinations of neural network architectures and training methods. 


## P3. Permutation equivariant neural networks

### Datasets for this question (Go to the OLD_datasets folder):

https://www.dropbox.com/sh/sztempv7hymr3ck/AADjIBGNJgKl9Ox7LcpKlgR7a?dl=0

Consider the problem of learning a permutation-equivariant function using a feedforward neural network with equivariant layers - see the lecture notes for definitions. The function we are going to consider corresponds to a choice function that for each set of input items outputs the choice of one of these items (using one-hot encoding).

We consider a feedforward neural network with L equivariant layers. Each of the first L-1 layers consists of an equivariant affine transformation followed by ReLU activation units with output dimension m x w. The output layer is an equivariant affine transformation with output dimension m.   

For the training, use Adam optimizer with the learning rate of 1e-4 and epsilon set to value 1e-3. For the loss function, use MSE. Use validation split of value 0.1. Use batch size of value 300. Use the number of epochs of value 100.

The training dataset is given in `xtrain-2.csv` and `ytrain-2.csv`. Each row of xtrain-2.csv contains values of a flatten m x d matrix (row concatenation). Each row of ytrain-2.csv contains elements of a m-dimensional output vector. The test dataset is given in `xtest-2.csv` and `ytest-2.csv` and is of the same format. In these datasets, m = 5 and d = 3.

**Task:**

- Implement the feedforward neural network defined above. Explain your implementation.
- Train the neural network with L = 5 and w = 2. Show the training and validation loss versus the number of epochs. Compute the test MSE value. Repeat this for (L,w) set to (2,10), (2,100), (2,200), (3,5), (3,10), (3,100), and (3,200). Discuss the obtained results. 

**Hint:**

- You may try implement the equivariant layers by using convolutional layers.

**Marking scheme**:

| **Problem breakdown** | **Max marks** | 
|-------------------|---------------|
| P1 correctness of implementation    |	10  |
| P1 discussion of results	|	10 |
| P2 network architecture design    |	10 |
| P2 use of different methods   | 10 |
| P2 achieved test error rates    |   10 |
| P2 discussion and presentation of results | 10 |
| P3 neural network implementation |  20 |
| P3 training and evaluation |  10 |
| P3 discussion and presentation of results | 10 |
| | Total 100 |
