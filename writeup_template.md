# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report




---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The first step, I converted to grayscale, applied a gaussian blur, and then canny edge detection to find the edges.  

Once I had that, I applied the region of interest function.  Initially, I had used a triangle instead of a trapezoid, but I was getting unwanted lines at the peak.  The examples provided showed a trapzeoid as well, so I thought it would be better anyway.

Finally, I applied the hough transform to get the lines.  Within the draw lines function, I realized I had a bunch of points which I could use to calculate a linear regression line.  Once I had this, I wanted the lines to extend to the y values, so I had calculate the x values from the two formulas.

[//]: # (Image References)
[alt text][image1]:./test_images_output/solidWhiteCurve.jpg "An example output"


### 2. Identify potential shortcomings with your current pipeline
Potential shortcomings include.
1) Assumes lanes are fairly straight.
2) Lanes are a narrow range of color.
3) Lanes are in a narrow region.
4) Probably woudln't work so well at night time.
5) Probably wouldn't work if there are similar color objects within the lane itself
### 3. Suggest possible improvements to your pipeline
1) Fix potential shortcomings above
2) Try different color ranges
3) Try to accommodate curve lines