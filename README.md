# Fashion_MNIST_Pytorch_refactored
Implementation of Convolution Nueral Network using Pytorch framework for the classification of Fashion MNIST dataset.

## About_Fashion_MNIST_dataset
Fashion MNIST dataset contains 70000 images from 10 different fashion categories. Dataset is a balanced dataset means it contains 7000 images from each category.
The dimension of each image is 1x28x28. All the images are grey scale image i.e. There is only single color channel.This data can be easily extracted,loaded and transformed
using torchvison API which comes preinstalled with torch package.

## About the convolutional nueral network used
The CNN which is used contains 2 convolution layers. First Conv2d layer accepts the single channel input and output the 6 channel. The kernal size used is 5x5.
Second layer accepts 6 channel input and produce 12 channel output.The kernal size here as well is 5x5.
Third layer is fully connected linear layer. It accepts 12x4x4 input feature after flattening the last conv 2d output.The output is 1x120 fully connected layer.
Fourth layer is also a fully connected layer which accepts a 120 dim (o/p from the last layer) and produce 1x60 dim output.
Final layer is the 1x10 dim output layer corresponding to 10 categories.

## About Coding style
The code has been refactored into multiple class in order to add the layers of abstraction and readibility. The RunManager class especially is created to track epoch loss,epoch
count and total no of correct prediction. The code is designed in such a way that it can accept different set og hyperparameters such as lr (leraning rate) ,batch_size and shuffle.The code also also saves the result of every run(cycles with different hyperparameters) in to local directory in .csv and ,json format. Additionally code also
add loss ,weights,gradient etc to tensorboard for sake of better visualisation.


