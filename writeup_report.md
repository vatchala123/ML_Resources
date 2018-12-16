# **Finding Lane Lines on the Road** 

## Writeup Template



---

**Finding Lane Lines on the Road**

[//]: # (Image References)

[image1]: ./output_images/mask_white.png "mask_white"
[image2]: ./output_images/hsl.png "hls"
[image3]: ./output_images/Grayscale.png "Grayscale"
[image4]: ./output_images/Gaussian.png "Gaussian"
[image5]: ./output_images/Canny.png "Canny"
[image6]: ./output_images/ROI.png "ROI"
[image7]: ./output_images/Hough_lines.png  "Hough_Lines"
[image8]: ./output_images/Hough_lines.png "Hough_Lines"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

In this project, I used Python and OpenCV to find the lane lines and creating averaged and extrapolated boundary line.
**My pipeline consists of following steps,**


1.Create masks for yellow and white pixels.
![alt text][image1]
![alt text][image2]

2.Convert white and yellow mask to gray scale image. 
![alt text][image3]

3.Apply Gaussian blur with kernel size=5. 
![alt text][image4]

4. Detect edges using canny edge detection. 
![alt text][image5]

5.Create Additional mask the resulting image to only include the region of interest. 
![alt text][image6]

6.Apply Hough transform to Hough lines.
![alt text][image7]

7.Draw extrapolated lines to extend over detected lane lines.
![alt text][image8]




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
