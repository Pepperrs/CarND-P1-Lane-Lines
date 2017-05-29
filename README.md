# Finding Lane Lines on the Road 

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of five steps. At first, I convert a given image zu grayscales to prepare for canny edge detection. Then I apply a gaussian blur filter to remove most unwanted edges. Step three detects edges in the image using the canny edge detection algorithm. After having cropped the region of interest in step 4 to approximated street levels, I calculate all lines using the hough transformation. before being drawn onto the image these lines get averaged and an average slope of the lines is calculated. This slope is then used to draw the resulting line onto the image.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when multiple lines are detected, even when they are not part of the lane line, they are used for generating the average of the displayed line. 

Another shortcoming could be that the algorithm has no way to properly identify a curve and will fail spectacularly in one.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to calculate points of origin for the line. I could calculate where a line segment had previously left the camera view and use this to approximate a broken line.

Another potential improvement could be to calculate the region of interest based on what can be identified as the road. This would allow the challenge video to net much better results, as currently there most portions of the sky are considered for lines.
