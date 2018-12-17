# **Finding Lane Lines on the Road** 

## Writeup Template

The goals / steps of this project are the following:
    Make a pipeline that finds lane lines on the road.
    Reflect on your work in a written report.


---

**Finding Lane Lines on the Road**

[//]: # (Image References)

[image1]: ./output_images/RGBtoHLSconverted.png "ConvertedHLSimage"
[image2]: ./output_images/HSLMASKED.png "hslmasked"
[image3]: ./output_images/Grayimage.png "Grayimage"
[image4]: ./output_images/Gaussian.png "Gaussian"
[image5]: ./output_images/Edges.png "Edges"
[image6]: ./output_images/Regionofinterest.png "ROI"
[image7]: ./output_images/Hough_Line.png  "Hough_Lines"
[image8]: ./output_images/annotated_solidYellowCurve2.jpg "Line_segment"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

In this project, I used Python and OpenCV to find the lane lines and creating averaged and extrapolated boundary line.
**My pipeline consists of following steps,**


1.Convert original image to HSL. 

![alt text][image1]

2.Isolate yellow and white from HSL image

3.Combine isolated HSL with original image

![alt text][image2]

4.Convert image to grayscale.
![alt text][image3]

5.Apply Gaussian Blur to smoothen the gray image for better edges detection.

![alt text][image4]

6.Apply Canny Edge Detection on smoothed gray image to detect edges

![alt text][image5]

7.Trace Region of Interest and discard all other lines identified by canny edge detection that are outside this region 

![alt text][image6]

8. Perform a Hough Transform to find lanes within our region of interest and trace them in red

![alt text][image7]

7.Draw extrapolated lines to extend over detected lane lines.

![alt text][image8]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function to calculating the mean slope for  left and right line. Based on those we are deciding the whether it right or left lane. Then I calculate the average of slopes and intercept and based on those finding the X co-ordinates(The line which have minimum value of y and I’m Considering as the y_min )


### 2. Identify potential shortcomings with your current pipeline

    
It only detects the straight lane lines. I could see curve lines in video, the same project can be extending for detecting curve lines.




### 3. Suggest possible improvements to your pipeline

1.One possible improvement could be to avoid shakiness of lines drawn in video .

2.Another possible improvement could be selecting the tuning parameters (vertices, threshold)


