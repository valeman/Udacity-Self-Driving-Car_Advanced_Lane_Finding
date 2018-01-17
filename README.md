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

The results could be observed on an image, whilst distorions could be subtle the difference is clearly seen in when we subtract two images (original and undistorted one) from each another. 

![distortion correction](/images/example_distortion_correction.png)

## Perspective transform

Perspective transform allows to take 'bird's eye' view of the image in order to facilitate image processing. In particular it allows to represent parallel left and righ lane markers are they are - parallel. 

Function M = cv2.getPerspectiveTransform(src,dst) allows to obtain matrix M to transform images into 'bird's eye' view, matrix MInv allows to make inverse transformation from 'bird's eye' view into driver's view. In order to perform PT, we obtain four points on the left and right lane markers. Upon transpormation trapezoid formed by the four points should be represented by rectangle.

<p align="center">
  <img src="images/perspective_transform_calibration.png" alt="perspective transform"/>
</p>





  


  
