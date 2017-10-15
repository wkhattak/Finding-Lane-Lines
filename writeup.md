# Project Writeup: Finding Lane Lines
 
## Overview   
   
This writeup reflects upon the "Finding Lane Line" project by explaining how the image processing pipeline works, identifying any shortcomings and proposing potential improvements. 


## Project Goals
The main goals of the **Finding Lane Line** project are:

1. Development of a code pipeline that finds lane lines on the road 
2. Reflection on the above pipeline in the form of a written report

## Reflection

### Pipeline

My image processing pipeline consisted of 8 steps as follows:

1. **Reading in an image:**

![Input Image](writup_images/input.jpg)

2. **Filtering out any non-white and non-yellow pixels:** This is done to make sure that only those pixels are processed later in the pipeline that belong to lane lines only. This helps with filtering out shadows, median, road surface colour change (gray/dark gray potentially due to resurfacing of a patch) that may give the impression of an actual line. This especially applies to the *challenge* video clip. The ```inRange()``` function was mainly used to create a mask along with the ```bitwise_and()``` function.

![White Yellow Masked Image](writup_images/white_yellow_image.jpg)