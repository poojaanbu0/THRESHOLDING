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
![Screenshot 2023-11-14 140804](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/303445db-1a9c-4c9e-993c-df8ddf2008fb)

### Global Thresholding:
![Screenshot 2023-11-14 141048](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/71f81cc4-9072-42ae-ac36-daf2b90d3b0b)

![Screenshot 2023-11-14 141114](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/1425d261-fab3-469d-a16f-7bb0b08dae46)

![Screenshot 2023-11-14 140908](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/9362c7ad-fd76-4d4e-9134-b9078c0358cc)

![Screenshot 2023-11-14 140923](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/fae3718c-6ad9-4284-b9c4-1de413ed0263)

![Screenshot 2023-11-14 141005](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/e61f3a8a-fb0b-42cb-973f-83fe1448ff8c)

![Screenshot 2023-11-14 141015](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/c0153fa3-d3b9-4804-b485-78e46b576a89)


### Adaptive Thresholding:
![Screenshot 2023-11-14 141015](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/3bd339f0-0276-41b7-b049-0b4400b35b56)

![Screenshot 2023-11-14 141023](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/f04b662a-e140-46ac-829b-0e07efad5bb4)


### Optimum Global Thesholding using Otsu's Method:
![Screenshot 2023-11-14 141114](https://github.com/poojaanbu0/THRESHOLDING/assets/119390329/f0ed1111-1f38-4c5c-9e5e-30a41dc923b5)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
