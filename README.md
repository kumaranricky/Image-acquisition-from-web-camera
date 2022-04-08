# Image-Acquisition-from-Web-Camera
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.
## Program:
``` Python
### Developed By:Kumaran.B
### Register No:212220230026

## i) Write the frame as JPG file

import cv2
import numpy as np
v1=cv2.VideoCapture(0)
while(True):
    ret,frame = v1.read()
    cv2.imwrite("log.jpg",frame)
    result = False
v1.release()
cv2.destroyAllWindows()





## ii) Display the video
v1=cv2.VideoCapture(0)
while(True):
    rel,frame=v1.read()
    cv2.imshow("log.jpg",frame)
    if cv2.waitKey(1)==ord('k'):
        break
v1.release() 
cv2.destroyAllWindows()




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
![Screenshot (41)](https://user-images.githubusercontent.com/75243072/162406177-e806b97d-ba86-4406-a316-9dcb4b6afbb9.png)

### ii) Display the video
![Screenshot (41)](https://user-images.githubusercontent.com/75243072/162406197-755e331d-8216-4a1f-89e2-e6020fed51c0.png)

### iii) Display the video by resizing the window
![Screenshot (42)](https://user-images.githubusercontent.com/75243072/162406223-0550c608-c81b-4a21-8ee4-aeae9910a618.png)

### iv) Rotate and display the video
![Screenshot (43)](https://user-images.githubusercontent.com/75243072/162406237-f2189a08-0bf7-464c-a72e-ce3310984418.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
