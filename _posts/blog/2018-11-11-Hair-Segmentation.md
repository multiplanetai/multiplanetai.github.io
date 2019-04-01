---
layout: default

title: "HS - Dense classification"
description: "How a hairstyle visualizer can change the world"
image: "/img/project1.png"
imagealt: "Default image"
date: 2018-11-11

projectname: "Hairstyle visualizer"
category: "blog"
published: true
comments: true
---

I was wrong I did very superficial research on how to approach the project.  My logic was to implement a program to understand how face-swap works in order to develop an algorithm that does the same but with hair. From that point, I would solve the first problem: how to know where exactly in the image the hair is located. If I had investigated well, I would have known that this problem is easily solved with a deep learning model for dense classification, so I could start the project from this point instead of starting from scratch. But well, now I'll always research more deeply before starting something.

Dense classification means to classify pixel by pixel an image into different categories. In this case, those categories are hair, face, and background. Once you classify all the pixel you can create a mask, from here the challenge: make a hair swap without change the properties of people's hair, begins. 

What I mean by not changing the properties of people's hair is that the project not just make a copy paste from one hairstyle to another. As an example, if a person has receding hairlines and chooses a hairstyle without them, then the hair-swap needs to add them.

There are more than two ways to perform a dense classification to segment the hair, but for the moment, I will only try two of them:
- Fully Convolutional Network.
- U-Net Network. 