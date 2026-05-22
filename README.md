# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation

## Developed By : HARINI S
 
## Program:

``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
def load_img():
    blank_img=np.zeros((600,600))
    font=cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='HARINI',org=(50,300), fontFace=font, fontScale=5, color=(255,255,255), thickness=25, lineType=cv2.LINE_AA)
    return blank_img
def display_img(img):
    fig=plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()
display_img(img)
white_noise=np.random.randint(low=0,high=2,size=(600,600))
white_noise=white_noise*255
noise_img=img+white_noise
display_img(noise_img)
kernel = np.ones((5,5), np.uint8)  # You can adjust the kernel size as needed (3,3), (5,5), (7,7), etc.

# Apply morphological opening (erosion followed by dilation)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
img=load_img()
black_noise=np.random.randint(low=0,high=2,size=(600,600))
black_noise=black_noise*-255
black_noise_img=img+black_noise
black_noise_img[black_noise_img==-255]=0
display_img(black_noise_img)
closing_image = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing_image)


```
## Output:

### Display the input Image
<img width="1061" height="699" alt="image" src="https://github.com/user-attachments/assets/83efc73c-75f7-4455-88cc-9b5583887ba7" />

### Noise Image
<img width="1140" height="673" alt="image" src="https://github.com/user-attachments/assets/2e58b719-3fa6-4b90-a9cd-b303a6c4faf3" />

<img width="1138" height="758" alt="image" src="https://github.com/user-attachments/assets/fd53b816-68f4-4ab9-8a7b-4dd0d2ac8177" />

### Display the result of Opening
<img width="1115" height="688" alt="image" src="https://github.com/user-attachments/assets/45966e2b-1387-46c2-8dfa-4cf373d11cf4" />

### Black noise Image

<img width="1143" height="671" alt="image" src="https://github.com/user-attachments/assets/3934355e-c3d0-4b86-8f0c-36c164187378" />


### Display the result of Closing
<img width="1212" height="607" alt="image" src="https://github.com/user-attachments/assets/fec605ef-734f-4856-94aa-527a6e579d8f" />


<br>
<br>

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
