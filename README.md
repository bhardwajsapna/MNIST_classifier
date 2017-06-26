# MNIST Neural Net Classifier

- An implementation of a simple neural network to classify handwritten digits of the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset
- This particular piece of code doesn't use any library to construct the neural net.

# DataSet

- The dataset is available [here](http://yann.lecun.com/exdb/mnist/).
- The dataset is split into 60,000 training images and 10,000 test images.
- Each image is a 28x28 pixel grayscale image, with 0.0 representing a pure white, 1.0 representing pure black and the numbers lying in between representing various shades of grey.
- Here the test images are left aside, and the training set is split into two parts, a set of 50,000 images to train the neural net and a separate 10,000 images as the validation set.

# Documentation of the code

- Network class Initialization:
	- the list `sizes` contains the number of neurons in the repective layers.
	- for example : a Network with 2 input layer neurons, 3 hidden layer neurons and 1 output layer nueron shall be represented as `net = Network([2, 3, 1])`.
	- The biases and the weights are initialised randomly (using Gaussian distributions of mean = 0 and standard deviation = 1) (implemented using numpy).
	- The biases and weights are stored as lists of numpy matrices. (There are no biases for the input layer, obviously)
	- The w(j,k) in weights[1] is representation of the weight for the connection between the kth neuron of the second layer and the jth neuron of the third layer.

- FeedForward:
	- a' = sigma(w*a + b); a is the vector activations of the second layer of neurons; a is multiplied by weight matrix w and added with vecotr b of biases. sigma is then applied element-wise to every entry in the vector (w*a + b).

- Stochastic Gradient Descent:
	- The neural network is trained using mini-batch SGD.
	- The training data is a list of tuples `(x, y)` representing the training inputs and the desired outputs.
	- If the test data is provided then the network will be evaluated against the test data after each epoch, and partial progress is printed.
	- Useful for tracking progress and to get a feel of how the network is trained (although it slows things down substantially).
	- Eta is the small, positive learning rate.

- Update Mini Batch:
	- Rule Updation program.
```````````````````````````````````````````` To be completed````````````````

# Python Package Dependencies

- `numpy`
- `cpickle`

# Running the neural net

```python
python run.py
```
