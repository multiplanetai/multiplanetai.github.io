---
layout: post

title: "IW - Facial landmark detection "
description: "How a hairstyle visualizer can change the world"
image: "/img/project1.png"
imagealt: "Default image"
date: 2018-07-27

projectname: "Hairstyle visualizer"
category: "blog"
published: true
comments: true
---

The first step of the image warping technique is detecting the facial features since they can be used to align facial images. Also, once you know a few landmarks points, you can estimate the pose of the head. In other words, you can figure out how the head is oriented in space, or where the person is looking. 

There are two famous datasets useful to create a model able to do facial landmark detection: [LFPW](https://neerajkumar.org/databases/lfpw/) and [HELEN](http://www.ifp.illinois.edu/~vuongle2/helen/). Also there is a library with pre-trained models that you can use for commercial applications called [Dlib](http://dlib.net/compile.html). 

If I decided to follow this path (after check thoroughly the encoder-decoder way) I will likely use the Dlib library and focus on creating a model to classify face geometry or improve the landmark detections in profile faces. In this way, I focus on the real problems and lose less time reinventing the wheel. 

In both cases, the face geometry classifier will be useful since the facial geometry of humans varies quite a bit. It can improve the face alignment on image warping, or it can be a simple preprocessing step for the encoder-decoder model. In fact, reading some papers related to landmark detection, I got a hypothesis/idea on how to improve the performance of an encoder-decoder model for face-swap. If we are capable of detecting critical visual features and discard quickly background regions of the image while spending more computation on promising object-like regions, we can improve the image encoding and speed up the conversion, therefore we will increase the conversion speed while maintaining the quality of it... 

