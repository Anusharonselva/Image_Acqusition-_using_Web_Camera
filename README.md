# Image_Acqusition-_using_Web_Camera
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
Import the cv2 and numpy package.
### Step 2:
Read the Video frame using the cv2.VideoCapture(0)
### Step 3:
Write the image using imwrite().
### Step 4:
Display the frame using the imshow().
### Step 5:
Divide the frame into halves and assign the smaller frame
## Program:
``` Python
### Developed By:S.ANUSHARON
### Register No:212222240010
```
## i) Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("oscar.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```
## ii) Display the video
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('OSCAR',frame)
    cv2.imwrite("MY_OSCAR.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('OSCAR ',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('OSCAR', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![WhatsApp Image 2024-02-28 at 7 21 45 AM](https://github.com/Anusharonselva/Image_Acqusition-_using_Web_Camera/assets/119405600/058d9ca6-dd6b-4c83-9a47-713665e1184f)

### ii) Display the video
![WhatsApp Image 2024-02-28 at 7 21 45 AM](https://github.com/Anusharonselva/Image_Acqusition-_using_Web_Camera/assets/119405600/b6ddd27e-b787-4b75-9390-c2a1f0e5f6d1)

### iii) Display the video by resizing the window


![WhatsApp Image 2024-02-28 at 7 21 57 AM](https://github.com/Anusharonselva/Image_Acqusition-_using_Web_Camera/assets/119405600/e2da73c5-4f22-4e87-888f-afa974ac768d)


### iv) Rotate and display the video
![WhatsApp Image 2024-02-28 at 7 21 51 AM](https://github.com/Anusharonselva/Image_Acqusition-_using_Web_Camera/assets/119405600/f174616a-036b-443c-8431-e6807c741212)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
