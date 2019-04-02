---
layout: post

title: "IW - Convex hull, Delaunay triangulation, and Affine warp"
description: "How a hairstyle visualizer can change the world"
image: "/img/project1.png"
imagealt: "Default image"
date: 2018-07-28

projectname: "Hairstyle visualizer"
category: "blog"
published: true
comments: true
---

After we performed the facial key points detection, we can use those points to perform convex hull. The boundary of a collection of points is called 'hull', and a boundary that doesn't have any concavities (None of their lines intersect inside the figure/polygon) is called 'convex hull'. So basically, we used the landmarks to draw a boundary of the face. We will use that boundary to divide the faces into smaller parts with an implementation of a Delaunay triangulation algorithm. 

Triangulation refers to the subdivision of the plane into triangles with the points as vertices (in this case the points that formed the convex hull). Obviously, a set of landmarks can have many possible triangulations, so what Delaunay triangulations does is to choose triangles such that no point is inside the circumcircle of any triangle. This will make the image invariant to scale and orientation differences and robust to the contamination of noises. 

Then, we consider the triangles between the source face and the target face, and affine warp the source face triangle onto the target face. An affine transform is the simples way to transform a set of three points to another set of arbitrary three points. It encodes translation, scale, rotation, and shear. We create a triangular mask by filling pixels inside the output triangle with white. This mask, when multiplied with the output image, turns all pixels outside the triangle black while preserving the color of all pixels inside the triangle. We use the mask to swap it into the target face, but the result hardly will look natural (because of lighting and skin tone differences between images)...


![Face aligment](../../../../postimgs/iw-face-aligment.png)

