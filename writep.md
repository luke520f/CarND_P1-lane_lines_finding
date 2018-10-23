# **Finding Lane Lines on the Road**

## Writeup

[//]: # (Image References)

[image1]: ./examples/blur_img.png "blur_img"
[image2]: ./examples/edges.png "edges"
[image3]: ./test_images_output/solidWhiteCurve.jpg "line_img"




### 1.Description of the pipeline
 
My pipeline consisted of 5 steps.First of all,I converted the images to grayscale.Then I applied Gaussian blur to the gray image in order to
get a smooth version of images.
Here is an example of an image after Gaussian blur

![alt text][image1]

I employed Canny edge detection to identitify the pixel edges in pictures and then selected only
interest regions that may include lane lines.Here is an example of an image after canny edges detection
![alt text][image2]

Finally,I applied hough lines transform to detect lines in the image and mark them as red color
In order to draw a single line on the left and right lanes,I modified the draw_lines() function by compute the the averge slope and 
the center position of each line.I set a slope threshold manually to avoid the influence of lighting noisy lines and I used the average
slope and center point to compute the start point and end point of left lane line and right lane line.


Here is an example image of the final result
![alt text][image3]


### 2.Identift potential shortcomings
There are two main potential shortcomings for my pipeline.
The first one is it may be influenced by the noise lines and output strange mark
Another shortingcoming is that some parameters have to be set manually beforehand so this pipeline is not
very robust and universal to different kinds of images.

### 3.Suggest possible improvements to my pipeline
A possible improvement would be to apply a noisy line filtering method to make it more robust
and use more advanced computer vision methods to avoid the influence of lighting.