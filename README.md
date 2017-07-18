# P1-lane-lines--Udacity-project
this is the first project in Udacity's nano degree "Self-driving car Engineer" SDCND

My pipeline consisted of 5 steps: 
1) converted the images to grayscale
2) applied Gaussian smoothing 
3) detected the lines using Canny edge detection
4) defined my ROI (region of interest)
5) applied Hough transform.

In order to draw a single line on the left and right lanes:
1) distinguish which points belong to the right line and which belong to the left line using the slope
2) add these point to training lists for a “linear regression classifier” since
      I know that these point are defined correctly and let the classifier
      predict the y-coordinate of the extrapolated x-coordinates
3) draw thelines using cv2.line () 

But when making the videos I defined the training lists as globals to
accumulate the training points resulting in a better classifier
performance with each frame

### 2. Identify potential shortcomings with your current pipeline
1) if the video is a life streaming, the accumulative lists will cause a memory overflow
2) when the car is turning the ROI will change but in my code it’s fixed so the result will be missy

### 3. Suggest possible improvements to your pipeline
1) make the lists hold the last number of frame’s points to prevent the system from overflowing
2) make a flexible ROI and somehow draw curves in addition to lines to do good curves detection.
