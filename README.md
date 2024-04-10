# THRESHOLDING
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
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("kong.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("kong.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/35634246-2ba6-4a52-9d6b-97a93f07b736)


### Global Thresholding
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/a3d08fab-a6ac-4f5b-a5df-a39aae39b8b9)
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/166acca7-eb12-4f4a-9262-719a1f730041)
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/304f1984-0c47-42b7-857e-df856a7e5509)
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/a847cc2e-5e8a-4558-a887-10ce7c2c3245)
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/c273b9d3-6858-4917-b3b9-ba0ec5891967)



### Adaptive Thresholding
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/d5d353d7-32c8-4940-9fde-f708b9480ed9)
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/dec5f107-447b-4ea1-a28c-f5dd4909148f)



### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/JEGADEESH07/THRESHOLDING-/assets/113497131/5a0b12a3-cf43-4b8b-bbd4-ae86fbbf31d5)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
