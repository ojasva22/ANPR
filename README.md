# ANPR
Automatic Number Plate Recognition Using OpenCV and Tesseract(Python)

Automatic number plate recognition (ANPR), also known as licence plate recognition (LPR), is a technology that reads vehicle registration plates. ANPR is widely used around the world by agencies such as the police force, traffic management facilities, toll agencies on pay-per-use roads, as well as parking management services.

LPR has 3 major stages.

a)License Plate Detection: This is the first and probably the most important stage of the system. It is at this stage that the position of the license plate is determined. The input at this stage is an image of the vehicle and the output is the license plate.
b)Character Segmentation: It’s at this stage the characters on the license plate are mapped out and segmented into individual images.
c)Character Recognition: This is where we wrap things up. The characters earlier segmented are identified here. We’ll be using machine learning for this.

Libraies used: OpenCV, TensorFlow, NumPy





128x64 was chosen as the input resolution as this is small enough to permit training in a reasonable amount of time with modest resources, but also large enough for number plates to be somewhat readable.

For each window the network should output:

The probability a number plate is present in the input image. (Shown as a green box in the above animation).

The probability of the digit in each position, ie. for each of the 7 possible positions it should return a probability distribution across the 36 possible characters. (For this project I assume number plates have exactly 7 characters, as is the case with most UK number plates).




A plate is considered present if and only if:

a) The plate falls entirely within the image bounds.

b) The plate’s width is less than 80% of the image’s width, and the plate’s height is less than 87.5% of the image’s height.

c) The plate’s width is greater than 60% of the image’s width or the plate’s height is greater than 60% of the image’s height.




Convolution Neural Netwoks

The architecture of a ConvNet is analogous to that of the connectivity pattern of Neurons in the Human Brain and was inspired by the organization of the Visual Cortex.
The role of the ConvNet is to reduce the images into a form which is easier to process, without losing features which are critical for getting a good prediction.

There are 2 main parameters that we can change to modify the behavior of each layer. After we choose the filter size, we also have to choose the stride and the padding.

Stride controls how the filter convolves around the input volume. In the example we had in part 1, the filter convolves around the input volume by shifting one unit at a time. The amount by which the filter shifts is the stride.

As we keep applying conv layers, the size of the volume will decrease faster than we would like. In the early layers of our network, we want to preserve as much information about the original input volume so that we can extract those low level features. Let’s say we want to apply the same conv layer but we want the output volume to remain 32 x 32 x 3. To do this, we can apply a zero padding of size 2 to that layer. Zero padding pads the input volume with zeros around the border.

 After each conv layer, it is convention to apply a nonlinear layer (or activation layer) immediately afterward.The purpose of this layer is to introduce nonlinearity to a system that basically has just been computing linear operations during the conv layers.
eg ReLu Layers

Dropout layers have a very specific function in neural networks. In the last section, we discussed the problem of overfitting.

 It makes sure that the network isn’t getting too “fitted” to the training data and thus helps alleviate the overfitting problem. An important note is that this layer is only used during training, and not during test time.

  A network in network layer refers to a conv layer where a 1 x 1 size filter is used. Now, at first look, you might wonder why this type of layer would even be helpful since receptive fields are normally larger than the space they map to. However, we must remember that these 1x1 convolutions span a certain depth, so we can think of it as a 1 x 1 x N convolution where N is the number of filters applied in the layer


Adding a Fully-Connected layer is a (usually) cheap way of learning non-linear combinations of the high-level features as represented by the output of the convolutional layer. The Fully-Connected layer is learning a possibly non-linear function in that space.

Now that we have converted our input image into a suitable form for our Multi-Level Perceptron, we shall flatten the image into a column vector. The flattened output is fed to a feed-forward neural network and backpropagation applied to every iteration of training.


IMAGE SEGMENTATION

https://github.com/Link009/LPEX/blob/master/Extraction.py
https://learndeltax.blogspot.com/2016/02/number-plate-detection-in-opencv-python.html
https://circuitdigest.com/microcontroller-projects/license-plate-recognition-using-raspberry-pi-and-opencv
https://pdfs.semanticscholar.org/2455/9fa9f8b5f18e88c0ebc3711554e99106915e.pdf
https://gist.github.com/nikgens/1a129d620978a4abc6a9a30f5f66e0d3
https://medium.com/@bhadreshpsavani/how-to-use-tesseract-library-for-ocr-in-google-colab-notebook-5da5470e4fe0

https://github.com/apoorva-dave/LicensePlateDetector
