# Deep_Learning_Style_transfer

Image Style Transfer Using Convolutional Neural Networks VGG19

In this notebook, we’ll recreate a style transfer method that is outlined in the paper, Image Style Transfer Using Convolutional Neural 
Networks, by Gatys in PyTorch.

In this paper, style transfer uses the features found in the 19-layer VGG Network, which is comprised of a series of convolutional and 
pooling layers, and a few fully-connected layers. In the image below, the convolutional layers are named by stack and their order in the 
stack. Conv_1_1 is the first convolutional layer that an image is passed through, in the first stack. Conv_2_1 is the first convolutional 
layer in the second stack. The deepest convolutional layer in the network is conv_5_4.


**How does it work?**

- We take input image and style images and resize them to equal shapes.
- We load a pre-trained Convolutional Neural Network (VGG19).
- Knowing that we can distinguish layers that are responsible for the style (basic shapes, colors etc.) and the ones responsible for the 
content (image-specific features), we can separate the layers to independently work on the content and style.
- Then we set our task as an optimization problem where we are going to minimize:

1) content loss (distance between the input and output images - we strive to preserve the content)
2) style loss (distance between the style and output images - we strive to apply a new style)
3) total variation loss (regularization - spatial smoothness to denoise the output image)

- Finally, we set our gradients and optimize the algorithm.

**Tools and Libraries**

1) Googla colab
2) Python
2) Deep Learning Library - Pytorch
