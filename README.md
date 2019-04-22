# PyTorch-Neural-Style-Transfer
A simple PyTorch implementation of Neural Style Transfer Algorithm.

# Neural Style Transfer
Neural Style Transfer is a process of modifying the style of an image while still preserving its content.Given an input image and a style image, we can compute an output image with the original content but a new style.It was outlined in Leon A. Gatys’ paper, [A Neural Algorithm of Artistic Style](https://arxiv.org/pdf/1508.06576.pdf), which is a great publication, and you should definitely check it out.

Input Image + Style Image -> Output Image (Styled Input)

## How does it work ? 
1. We take input image and style images and resize them to equal shapes.

2. We load a pre-trained Convolutional Neural Network(VGG19).

3. Knowing that we can distinguish layers that are responsible for the style (basic shapes, colors etc.) and the ones responsible for the  content (image-specific features), we can separate the layers to independently work on the content and style.

4. Then we set our task as an optimization problem where we are going to minimize:
      * __Content Loss__ (distance between the input and output images - we strive to preserve the content)
      * __Style Loss__(distance between the style and output images - we strive to apply a new style)
      * __Total Loss__ = __Content Loss__ + __Style Loss__
      * Finally, we set our gradients and optimize with the [L-BFGS](https://en.wikipedia.org/wiki/Limited-memory_BFGS) algorithm.

# Results

I trained my model on Google Colab as they provide a Tesla K80. If you want to run it on your local system make sure to comment out where I have mounted the drive and use your local paths for the __Content__ and __Style__ images.

![image](https://github.com/Atharva-Phatak/PyTorch-Neural-Style-Transfer/blob/master/Results/macchu-pichu.jpg)
![image](https://github.com/Atharva-Phatak/PyTorch-Neural-Style-Transfer/blob/master/Results/galaxy%20(2).jpg)
![image](https://github.com/Atharva-Phatak/PyTorch-Neural-Style-Transfer/blob/master/Results/Cat_new.jpg)
![image](https://github.com/Atharva-Phatak/PyTorch-Neural-Style-Transfer/blob/master/Results/street_sky.jpg)

# References
* A Neural Algorithm of Artistic Style : (https://arxiv.org/pdf/1508.06576.pdf)
* Artistic Style Transfer with Convolutional Neural Network : (https://medium.com/data-science-group-iitr/artistic-style-transfer-with-convolutional-neural-network-7ce2476039fd)
* Neural Style Transfer Tutorial : (https://towardsdatascience.com/neural-style-transfer-tutorial-part-1-f5cd3315fa7f)

# Dependencies
* Python 3.6
* PyTorch 
* Torchvision
* PIL
* Matplotlib
* Numpy 
