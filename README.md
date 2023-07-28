# People-recognition

This Python code uses the OpenCV library and the imutils library to perform pedestrian detection on an input image. The pedestrian detection is based on Histogram of Oriented Gradients (HOG) and non-maximum suppression techniques.

The steps are as follows: 

1. Import necessary libraries:
- import cv2
- from imutils.object_detection import non_max_suppression
- from imutils import resize
- import numpy as np

2. Initialize the HOG descriptor for pedestrian detection:
- hog = cv2.HOGDescriptor()
- hog.setSVMDetector(cv2.HOGDescriptor_getDefaultPeopleDetector())
  
the Histogram of Oriented Gradients (HOG) descriptor is created and set with a pre-trained Support Vector Machine (SVM) detector for pedestrian detection.

3. Read and resize the input image:
- img = cv2.imread('d.jpg')
- img = resize(img, height=500)
  
The code reads an image called 'd.jpg' and then resizes it to a height of 500 pixels while maintaining the aspect ratio. Of course we can give any height we want. 

4. Perform pedestrian detection using HOG:
- rects, weights = hog.detectMultiScale(img, winStride=(4, 4), padding=(8, 8), scale=1.05)

The detectMultiScale function is used to perform pedestrian detection. It takes the resized image and returns a list of bounding boxes (rects) where pedestrians are detected and their corresponding weights (confidences).

5. Draw bounding boxes around detected pedestrians (before non-maximum suppression):
- copy = img.copy()
- for x, y, w, h in rects:
    - cv2.rectangle(copy, (x, y), (x+w, y+h), (0, 0, 255), 2)

6. 
 <img src="before.jpg">

 <img src="after.jpg">
