# Handwritten Digits Classifier on the MNIST dataset using a CNN

In this repo we built a handwritten digits classifier using Keras. Keras is a high–level neural networks API capable of running on top of TensorFlow (which is an open source machine learning framework). Convolutional neural networks are more sophisticated and offer higher accuracy than a simple multi-layer perceptron model. Keras provides many functionalities for creating convolutional neural networks easily. The code for can be found in “mnist.py”.

The first step is to import the classes and functions needed. Then, we need to load the MNIST dataset and reshape it so that it is suitable for use training a CNN. In Keras, the layers used for two-dimensional convolutions expect pixel values with the dimensions [pixels][width][height]. MNIST consists of grey scale images, hence the pixel dimension is set to 1. The pixel values are normalized to the range of 0 and 1 by dividing them by 255.

Next, we define our sequential neural network model.
1. The first layer is called Convolution2D. This layer has 32 feature maps, each with the size of 5×5 and a rectifier activation function. This is the input layer, expecting images with the structure outline above [pixels][width][height].
2. Then, we define a pooling layer called MaxPooling2D. It is configured with a pool size of 2×2.
3. We add another convolutional layer with 64 feature maps, each with a size 3x3 and having a rectifier activation function followed by a pooling layer with a pool size 2x2.
4. The next layer converts the 2D matrix data to a vector called Flatten. It allows the output to be processed by standard fully connected layers.
5. The next layer is a fully connected layer with 128 neurons and a rectifier activation function.
6. Finally, the output layer has 10 neurons for the 10 classes and a softmax activation function to output probability-like predictions for each class.

The CNN is fit over 10 epochs with a batch size of 200. Running the example, the accuracy on the training and validation test is printed each epoch and at the end of the classification error rate is printed. The figure below shows a screenshot of the result. We could achieve an accuracy of 99.19%.

![Training](https://github.com/csaiprashant/ocr_mnist_keras/blob/master/training.png)
