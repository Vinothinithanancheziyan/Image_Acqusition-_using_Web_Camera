# Image_Acqusition-_using_Web_Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
### Step 3:Use cv2.imread to read the video or image
<br>


### Step 4:Use cv2.imshow to show the video
<br>

### Step 5:End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: VINOTHINI T 
### Register No:212223040245

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    
    result = False
videoCaptureObject.release()
cv2.DestroyAllWindows()


## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()





## iii) Display the video by resizing the window


import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video



import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image
![WIN_20250708_13_22_31_Pro](https://github.com/user-attachments/assets/e67776db-907d-488a-96cc-7f056ff3e290)






### ii) Display the video

![WIN_20250708_13_22_31_Pro](https://github.com/user-attachments/assets/e67776db-907d-488a-96cc-7f056ff3e290)





### iii) Display the video by resizing the window

<img width="324" height="489" alt="Screenshot 2025-09-29 100742" src="https://github.com/user-attachments/assets/e67776db-907d-488a-96cc-7f056ff3e290" />







### iv) Rotate and display the video
<img width="372" height="484" alt="Screenshot 2025-09-29 100824" src="https://github.com/user-attachments/assets/9ee82a54-2f0d-40af-8067-539a5358e4ef" />






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
