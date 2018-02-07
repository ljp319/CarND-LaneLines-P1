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
	converte the images to grayscale;
	gaussian smoothing/blur with kernal size 5;
	Canny edge detection;
	mask image with region of interest;
	hough transform to find lines in image and draw them


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating gradient and extending the line to get extrapolated single line, the result is like this:


![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when no line detected in one frame, then impossible to calculate the gradient and draw lines.



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to save gradient or lines of last frame and draw it on current frame, or skip current frame if no line detected. 

