## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.


## Program

#### Name : Iswarya P
#### Register no : 212223230082

### Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read and show the Original image
```
image = cv2.imread('tj.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/a0c3dcd3-190d-4e0a-9ab6-d34342a947ea)

### Convert the image to grayscale
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/f8aec7dd-8387-4d60-98f1-b61950dea558)

### Use Global thresholding to segment the image
```
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/6a149159-779c-4ba7-873e-ade027cfbc33)

### Use Adaptive thresholding to segment the image
```
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```

### Output:
![image](https://github.com/user-attachments/assets/26644476-c011-44bd-8fdb-715052d2069e)

### Use Otsu's method to segment the image 
```
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/9c61c5e2-3c5d-4cca-9c7f-6b16e6db26f0)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
