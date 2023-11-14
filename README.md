# EXP-9 RECORD-THRESHOLDING
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1.Anaconda - Python 3.7,
2.OpenCV.

## Algorithm:
### Step 1:
Load the necessary packages requiured for the processing the threshold of the image.

### Step 2:
Read the Image using the cv2 instructions and convert it to a grayscale image.

### Step 3:
Apply global thresholding on the grayscale image and store the results in threshold variables. Use different thresholding methods to segment the image.

### Step 4:
Apply adaptive thresholding on the grayscale image and store the results in the variables th1 and th2. Use different adaptive thresholding methods to segment the immage.

### Step 5:
Apply Otsu's method on the grayscale image and store the result in variable th3.

### Step 6:
Create a list titles containing the titles of each image and a list images containing the corresponding images.

### Step 7:
Loop through the images list to display each image alongside its title using plt.subplot(), plt.title(), plt.imshow(), plt.axis(), and plt.show().

### Step 8:
End the program.

## Program:
```
Program to segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.
Developed By: Pooja A
Register Number:212222240072
```
```python
# Load the necessary packages:

import cv2
import matplotlib.pyplot as plt
import numpy as np
```
```python
# Read the Image and convert to grayscale:

image=cv2.imread("carss.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```
```python
# Use Global thresholding to segment the image:

ret, thresh1 = cv2.threshold(image1,100,220,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,90,160, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,140,220,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,225,270,cv2.THRESH_TOZERO_INV)
```
```python
# Use Adaptive thresholding to segment the image:

th1 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 3)
th2 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 3)
```
```python
# Use Otsu's method to segment the image:

ret2, th3 = cv2.threshold(image1, 150, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
```python
# Display the results:

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (Truncate)",
       "Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)","Otsu"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

## Output:
### Original Image:
![WhatsApp Image 2023-11-14 at 11 44 40_6231d6c1](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/c589b977-8100-419c-9b78-3a2d24d88d47)

### Global Thresholding:
![WhatsApp Image 2023-11-14 at 11 47 08_181c2c0e](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/1f24ef69-00e8-4226-a148-f2f894dad6a0)

![WhatsApp Image 2023-11-14 at 11 48 27_9068e49c](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/84ed801c-3c0d-49e8-b1a7-22a7d8a364aa)

### Adaptive Thresholding:
![WhatsApp Image 2023-11-14 at 12 03 24_f3279a8c](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/d87a38fa-3db7-43be-a50f-70751aa2ae4c)

### Optimum Global Thesholding using Otsu's Method:
![WhatsApp Image 2023-11-14 at 12 07 05_7591cd36](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/a2e25c14-5694-4821-a6aa-ab1fc742fb2a)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
