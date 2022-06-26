## EX.NO: 02<br>
## DATE: 08-04-2022
## <p align="center">IMAGE ACQUISITION FROM WEB CAMERA</p>
 
## Aim:
<br>
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
<br>
i) Write the frame as JPG 
<br>ii) Display the video 
<br>iii) Display the video by resizing the window
<br>iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm

### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("JayashreeRao.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
display the image until the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:

### Developed By: P S Chetan
### Register No: 212220230033

### i) Write the frame as JPG file
```python
import cv2

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("JayashreeRao.jpg",frame)
```

### ii) Display the video
```python
import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("JayashreeRao",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()
```

### iii) Display the video by resizing the window
```python
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

    cv2.imshow("JayashreeRao.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video
```python
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

    cv2.imshow("JayashreeRao.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![image](https://user-images.githubusercontent.com/74660507/161384406-a66c146b-391f-442b-9ad1-2f4f356715db.png)

### ii) Display the video

![image](https://user-images.githubusercontent.com/74660507/161384422-92e2ed7b-a2dc-496c-8063-172615adfcc9.png)

### iii) Display the video by resizing the window

![image](https://user-images.githubusercontent.com/74660507/161384444-ca840796-8cfc-41c9-89e7-955d83833836.png)

### iv) Rotate and display the video

![image](https://user-images.githubusercontent.com/74660507/161384458-f144bff1-301b-4f89-8b6b-518f4c22c90a.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
