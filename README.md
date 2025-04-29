# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step 2:
Read the Image and convert to grayscale.
### Step 3:
Use Global thresholding to segment the image.
### Step 4:
Use Adaptive thresholding to segment the image.
### Step 5:
Use Otsu's method to segment the image.
### Step 6:
Display the results.

## Program
```
Developed by: Sanjay Balaji S
Register No: 212223240149
```
### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread("dodge.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dodge.jpg",0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
## Output

### Original Image
![image](https://github.com/user-attachments/assets/ad0e1451-c354-4e95-8310-5eb223eb6e5e)


### Global Thresholding
![image](https://github.com/user-attachments/assets/9e9068b0-e80e-45f9-ad22-7f945e25eb84)
![image](https://github.com/user-attachments/assets/11622e66-4203-43ee-ae2f-19371e12740d)
![image](https://github.com/user-attachments/assets/cac1789a-7fa0-499e-8f14-bbe5c44eba8e)
![image](https://github.com/user-attachments/assets/25764b75-d0c5-4c24-8c1a-e874b86028bf)
![image](https://github.com/user-attachments/assets/11274999-5464-472d-89ae-966d82aa3dc5)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/0167795a-d2f2-4e51-a566-ccc31075f352)
![image](https://github.com/user-attachments/assets/bb88b595-76bd-4a44-875a-0ed5896a136e)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/394a8da1-650c-4666-bbee-54324bd1a296)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
