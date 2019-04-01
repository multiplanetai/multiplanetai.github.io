---
layout: default

title: "IW - Seamless cloning"
description: "How a hairstyle visualizer can change the world"
image: "/img/project1.png"
imagealt: "Default image"
date: 2018-08-08

projectname: "Hairstyle visualizer"
category: "blog"
published: true
comments: true
---

The previous result looks pretty bad, to solve it we can apply the seamless cloning technique and improve it exponentially. With this technique, you can copy an object from one image, and paste it into another making a composition that looks seamless and natural. 

In OpenCV, it is an implementation of the paper called [Poisson Image Editing](http://www.irisa.fr/vista/Papers/2003_siggraph_perez.pdf) which says that working with image gradients instead of image intensities can produce much more realistic results.  So, if we blend the intensities (RGB values) of the source image with the destination image using a carefully created mask we will obtain a better edition result.

With seamless cloning: 

The intensity of the resulting image in the masked region is not the same as the intensity of the source image region in the masked region. Instead, the gradient of the resulting image in the masked region is about the same as the gradient of the source region in the masked region.

The intensity of the resulting image at the boundary of the masked region is the same as the intensity of the destination image.  


![Face aligment](../../../../img-posts/hairstyle/iw-seamless-cloning.png)
