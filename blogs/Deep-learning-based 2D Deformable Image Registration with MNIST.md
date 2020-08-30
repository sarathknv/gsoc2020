# Deep-learning-based 2D Deformable Image Registration with MNIST

I’ve been accepted into [Google Summer of Code 2020](https://summerofcode.withgoogle.com/) under the [International Neuroinformatics Coordinating Facility](https://www.incf.org/) (INCF), and I will be working with the organization [Diffusion Imaging in Python](https://www.dipy.org/) (DIPY) in developing deep-learning-based image registration methods.  
  
  
Link to the project — [MRI Registration using Deep Learning and Implementation of Thin-Plate Splines](https://summerofcode.withgoogle.com/projects/#6582514342166528)  
  
  
Before the official coding phase started, I had developed a proof of concept for deep-learning-based deformable image registration using the MNIST dataset, taking ideas from these papers:
- [An Unsupervised Learning Model for Deformable Medical Image Registration](http://openaccess.thecvf.com/content_cvpr_2018/papers/Balakrishnan_An_Unsupervised_Learning_CVPR_2018_paper.pdf)  
- [Non-rigid image registration using fully convolutional networks with deep self-supervision](https://arxiv.org/pdf/1709.00799.pdf)  
- [End-to-End Unsupervised Deformable Image Registration with a Convolutional Neural Network](https://arxiv.org/pdf/1704.06065.pdf) 
  

Link to the Colab notebook — https://colab.research.google.com/drive/1fTzz1aT2sb8oAXRO1-dr6O_IR6dof36e?usp=sharing


## What is image registration?
Image registration is the process of finding a transformation that aligns one image to another. Generally, the inputs to this process are two images: a reference image also known as a static image, and a moving image that will be aligned to the static image. The goal here is to warp and match the moving image to the static image.  

## How to warp the image?  
Given a moving image and the static image as inputs, the convolutional encoder-decoder network computes the pixel-wise deformation between the two images. This deformation field also called a registration field, gives the new sampling locations in the moving image. The transformed image is obtained by sampling the moving image at these locations. Simply put, we are just rearranging the pixels in the moving image until it matches the static image as much as possible. The framework is as shown in the figure below.
<p align="center"> 
  <img src="_images/1_framework.png">
</p>

