# Thresholding

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
![image](https://github.com/user-attachments/assets/da841c2f-e382-4226-8e5f-f3820c56c020)

### Convert the image to grayscale
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/dd7c1349-c4b1-46af-9457-4eb97e23a8cd)

### Use Global thresholding to segment the image
```
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/b631e137-5cb9-4e08-81ef-e49e5b3b15ff)

### Use Adaptive thresholding to segment the image
```
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/4b113d07-7993-4ee6-9362-c268df9712f7)

### Use Otsu's method to segment the image 
```
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/294ffc89-9bfd-4acf-a816-7d2ad8021a58)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
