# Image Capture and Video Processing Using OpenCV
## Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
## SOFTWARE USED:
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
## ALGORITHM:
### Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using cv2.imwrite().

### Step 4:
Display the live video stream using cv2.imshow().

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## PROGRAM

### i) Write the frame as JPG file
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

<img width="392" height="325" alt="image" src="https://github.com/user-attachments/assets/79ac8ef5-6a95-41f3-9324-729b5ebcb750" />


### ii) Display the video

```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
````

<img width="375" height="290" alt="image" src="https://github.com/user-attachments/assets/8e24c61d-3c8a-4129-8240-7fc36f1fa2b8" />


### iii) Display the video by resizing the window

```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

<img width="217" height="306" alt="image" src="https://github.com/user-attachments/assets/6d522889-d6af-4194-a533-a6d24521110d" />


### iv) Rotate and display the video

```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

<img width="262" height="317" alt="image" src="https://github.com/user-attachments/assets/bed698b4-4a5e-4fc1-bd57-ec83d35adf22" />


## Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV. 
