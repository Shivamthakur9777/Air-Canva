# This Python script creates a virtual drawing board using OpenCV. It allows users to draw on a canvas by moving a colored object in front of their webcam. The script utilizes color detection and contour tracking to identify the colored object and track its movements.

Key Components:

Trackbars for Color Adjustment:

The script begins by creating a window named "Color detectors" with trackbars for adjusting the upper and lower HSV (Hue, Saturation, Value) ranges. These ranges are used to detect a specific color in the video feed.
Color Points Arrays:

Four deques (double-ended queues) are initialized to store the points of different colors: blue, green, red, and yellow. These points are used to draw on the canvas.
Canvas Setup:

A blank white canvas (paintWindow) is created where the drawings will be displayed.
Webcam Capture:

The script captures video from the default webcam using cv2.VideoCapture(0) and continuously reads frames from the webcam.
Frame Processing:

Each frame is flipped horizontally for a mirror effect and converted to the HSV color space.
The HSV values from the trackbars are retrieved and used to create an HSV mask that isolates the specified color.
Drawing Interface:

The script adds buttons for selecting colors and a "CLEAR ALL" button to clear the canvas. These buttons are drawn on the frame using rectangles and text.
Color Detection and Tracking:

Contours are found in the HSV mask to detect the colored object.
If a contour is detected, the script calculates the center of the contour and checks if it intersects with any of the buttons.
If the contour intersects with a color button, the drawing color is changed. If it intersects with the "CLEAR ALL" button, the canvas is cleared.
If the contour does not intersect with any buttons, the center point of the contour is added to the corresponding color's deque, allowing the user to draw.
Drawing on Canvas:

The points in the deques are used to draw lines on both the canvas and the video frame.
The script loops through the points arrays and uses cv2.line to draw lines between consecutive points.
Display Windows:

The script displays three windows: the live video feed with the drawing interface, the canvas, and the mask showing the detected color.
Exit Condition:

The script exits when the 'q' key is pressed, releasing the webcam and closing all OpenCV windows.
Usage:

Adjust the trackbars to set the HSV range for the color you want to use as a marker.
Move the colored marker in front of the webcam to draw on the virtual canvas.
Click on the color buttons to change the drawing color.
Click on the "CLEAR ALL" button to clear the canvas.
Press 'q' to exit the application.
This script provides an interactive way to draw on a virtual canvas using simple color-based object tracking, making it a fun and educational project for learning computer vision techniques with OpenCV.


# Shivam Singh