# **Finding Lane Lines on the Road**

### 1. Describe

My pipeline consisted of 6 steps.
1. Converts the image from RGB color space to GRAY color space.
2. Using a Gaussian filter before finds edges.
2. Finds edges in the image using the Canny86 algorithm.
3. Using cv2.fillPoly and cv2.bitwise_and to get the area we care about
4. Using cv2.HoughLinesP find lines and get a average line segments
5. Using cv2.fillPoly and cv2.bitwise_and again to get the line we care about
6. Merge line picture and original picture

In the draw_lines function I use slope to distinguish which is left line or right line.
In order to draw a single line on the left and right lanes, I get a average line segments and ignore some lines which slope is abnormal.
Finally,I draw two lines through the image.


### 2. Identify potential shortcomings with your current pipeline

When the Car turns or there is something in the road, the program will be confused.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ignore the edges area we not care about on the road.

Another potential improvement could be to combining the results of color recognition.
