# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>

### Step 2:
<br>

### Step 3:
<br>

### Step 4:
<br>

### Step 5:
<br>

## Program:
``` Python
### Developed By:Kumaran.B
### Register No:212220230026

## i) Write the frame as JPG file
import cv2
import numpy as np
v1=cv2.VideoCapture(0)




## ii) Display the video




## iii) Display the video by resizing the window
v2=cv2.VideoCapture(0)
while True:
    ret,frame=v2.read()
    width=int(v2.get(3))
    height=int(v2.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame,(0,1),fx=0.5,fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow("kum",image)
    if cv2.waitKey(1)==ord('k'):
        break
v2.release() 
cv2.destroyAllWindows()


## iv) Rotate and display the video
v2=cv2.VideoCapture(0)
while True:
    ret,frame=v2.read()
    width=int(v2.get(3))
    height=int(v2.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame,(0,1),fx=0.5,fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow("kum",image)
    if cv2.waitKey(1)==ord('k'):
        break
v2.release() 
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
</br>
</br>


### ii) Display the video
</br>
</br>


### iii) Display the video by resizing the window
</br>
</br>



### iv) Rotate and display the video
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
