# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().



### Step2
Convert the saved BGR image to RGB using cvtColor().



### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.



### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().



## Program:
### Developed By   :Vijay R
### Register Number:212221230121


### 1. Smoothing Filters

i) Using Averaging Filter
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("vj.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")


```
ii) Using Weighted Averaging Filter
```Python


kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")


```
iii) Using Gaussian Filter
```Python


gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")



```

iv) Using Median Filter
```Python

median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")



```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python

kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")



```
ii) Using Laplacian Operator
```Python

laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")



```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

[img1](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img1.png)
ii) Using Weighted Averaging Filter
[img2](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img2.png)

iii) Using Gaussian Filter
[img3](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img3.png)

iv) Using Median Filter

[img4](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img4.png)
### 2. Sharpening Filters


i) Using Laplacian Kernal
[img5](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img5.png)

ii) Using Laplacian Operator

[img6](https://github.com/vijay21500269/Implementation-of-Filters/blob/main/img6.png)
## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
