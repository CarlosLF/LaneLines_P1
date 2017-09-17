# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.


My pipeline consisted of 5 steps: 

1) First, I converted the images to grayscale, 
2) Then I apply the Gaussian blur and compute the image edges, 
3) Then I Mask the image, 
4) after that I compute the lines using the Hough transform, 
5) Compute the left and right lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function to estimate the left and right lines. First I separate the two sets using the slopes. For each set I estimate a line using liner regresion.

The result was the following:

![alt text][image1]

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the Hough algorithms finds lines that don't belog to the road images.

Another shortcoming could be that road lines couln't be detected due to the low image contrast.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to discard lines based on its slope.

Another potential improvement could be to convert the image to HSV, mask the image based on the yellow and white color, and the apply the proposed pipline.

