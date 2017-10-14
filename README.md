
#Project: Finding Lane Lines

---   
##Overview   
   
This project is about finding lane lines using [Open CV](https://opencv.org/) library. Either individual images can be fed or a video clip can be used as an input. 

---
## How Does It Work?
The logic comprises of an image processing pipeline comprising the following steps:

1. Reading in an image 
2. Filtering out any non-white and non-yellow pixels
3. Converting images to Gray scale
4. Performing edge detection on Gray scale image
5. Applying a mask on the detected edges so that only the area where the left/right lanes appear is kept
6. Applying Hough transformation to identify lines
7. Finding which lines belong to left lane lines and which lines belong to right lane lines from the previous step 
8. Finally extrapolating these left/right lines to get the a pair of left/right lane lines drawn on the original image.

For video clips, same logic is applied by processing individual frames.

##Directory Structure
----
* test_images: Directory containing sample images for testing
* test_images_output: Directory containing processed images
* test_videos: Directory containing sample videos for testing
* test_videos_output: Directory containing processed videos
* P1.html: Html output of the Python notebook
* P1.ipynb: Python notebook containing the source code
* README.md: Project readme file
* writeup.md: project writeup file containing detailed information about the inner workings of this project

##Requirements
----
* Python-3.5.2
* OpenCV-3.3.0
* numpy
* matplotlib
* moviepy


## Usage
**Images**

```python
image_list = os.listdir("test_images/")
for image_name in image_list:
    full_image_path = 'test_images/' + image_name
    find_lane_lines_raw(full_image_path)
```

**Video**

```python
white_output_raw = 'test_videos_output/raw-solidWhiteRight.mp4'
clip1_raw = VideoFileClip("test_videos/solidWhiteRight.mp4")
white_clip_raw = clip1_raw.fl_image(process_image_raw_lines) 
%time white_clip_raw.write_videofile(white_output_raw, audio=False)
```

##Troubleshooting

**ffmpeg**

NOTE: If you don't have ffmpeg installed on your computer you'll have to install it for moviepy to work. If this is the case you'll be prompted by an error in the notebook. You can easily install ffmpeg by running the following in a code cell in the notebook.

```python
import imageio
imageio.plugins.ffmpeg.download()
```

Once it's installed, moviepy should work.

##License
The content of this project is licensed under the [Creative Commons Attribution 3.0 license](https://creativecommons.org/licenses/by/3.0/us/deed.en_US).