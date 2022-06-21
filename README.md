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
![Screenshot (41)](https://user-images.githubusercontent.com/75243072/173754492-64e0fa05-d3c9-47c4-b755-8f37fa73bf45.png)

### <br><br><br><br><br><br><br>ii) Display the video
![Screenshot (41)](https://user-images.githubusercontent.com/75243072/173754514-e4b989c7-dbf7-4254-9b57-3bedcfdc07ac.png)

### <br><br><br><br><br><br><br><br><br><br><br> iii) Display the video by resizing the window
![Screenshot (42)](https://user-images.githubusercontent.com/75243072/173754559-ec3a1d03-7fee-437b-a79c-a80e980a2229.png)

###  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>iv) Rotate and display the video
![Screenshot (43)](https://user-images.githubusercontent.com/75243072/173754596-cd0bfcb6-a69e-4600-832d-3347891ec923.png)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
