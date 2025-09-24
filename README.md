# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## Code : 
~~~

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('boy.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')


sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5) 
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

~~~
## Output:
### SOBEL EDGE DETECTOR

<img width="444" height="349" alt="image" src="https://github.com/user-attachments/assets/0b7283bd-5386-4535-8bb8-c054c1ddae78" />


### LAPLACIAN EDGE DETECTOR
<img width="434" height="344" alt="image" src="https://github.com/user-attachments/assets/65237c76-5aba-40fa-ad37-28910cf04ad1" />




### CANNY EDGE DETECTOR
<img width="454" height="346" alt="image" src="https://github.com/user-attachments/assets/a9577a00-1a49-4f1d-aac9-5c4c380e1d0e" />

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
