
# Project Writeup: Finding Lane Lines
 
## Overview   
   
This writeup reflects upon the "Finding Lane Line" project by explaining how the image processing pipeline works, identifying any shortcomings and proposing potential improvements. 


## Project Goals
The main goals of the **Finding Lane Line** project are:

1. Development of a code pipeline that finds lane lines on the road 
2. Reflection on the above pipeline in the form of a written report

## Reflection

###Pipeline

My image processing pipeline consisted of 8 steps as follows:

1. Reading in an image 
2. Filtering out any non-white and non-yellow pixels
3. Converting images to Gray scale
4. Performing edge detection on Gray scale image
5. Applying a mask on the detected edges so that only the area where the left/right lanes appear is kept
6. Applying Hough transformation to identify lines
7. Finding which lines belong to left lane lines and which lines belong to right lane lines from the previous step 
8. Finally extrapolating these left/right lines to get the a pair of left/right lane lines drawn on the original image. 

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.