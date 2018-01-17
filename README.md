# Udacity-Self-Driving-Car_Advanced_Lane_Finding
**Project: Advanced Lane Finding** 
Lane finding is an important component of self-driving cars, the lane finding algorithms should be robust to change in road types, lightining and weather conditions and curvature of the road. In this project, I have built algorithm to identify left and right lanes based on the images from dash-mounted camera video. The algorithm uses advanced computer vision techniques to detect lanes, locate the car between two lanes and estimate curvature of the road.

The project is organised by the following sections:

* Camera calibration
* Applying perspective transform
* Detecting Lane Lines
* Colour and channel thresholding
* Finding the lanes. Polynomial fitting.
* Measuring curvature
* Image processing pipeline

## Camera calibration

Before processing dashcam videos we have to calibrate camera in order to undistort distortions introduced by camera lense. This is performed by using chessboard, 20 chessboard images are processed by the OpenCV function cv2.findChessboardCorners which locates corners in the chessboard image.
![chessboard](/images/chessboard.png)

The located corners are then mapped to the real chessboard and mapping matrix obtained allowing to undistore images coming from the dashcam.

The results could be observed on an image:

![distortion correction](/images/example_distortion_correction.png)

## Perspective transform



  


  
