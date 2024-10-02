# THRESHOLDING
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:

### Step 1:
Load the necessary packages.
### Step 2:
Read the Image and convert to grayscale
### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:

Use Otsu's method to segment the image and display the results.

## Program:
```
Developed By: SWATHI D
Register Number: 212222230154
```

### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread('8 P.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('8 P.jpg',0)
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
## Output:

### Original Image
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/303c4ced-e2ad-4c1e-ad93-73b13744410b)
![Screenshot 2024-10-02 134538](https://github.com/user-attachments/assets/de498361-057c-4e38-a810-1f84f9b6a16a)




### Global Thresholding

![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 134711](https://github.com/user-attachments/assets/57844364-ea54-4d21-ac44-aa9f0f667781)
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/303c4ced-e2ad-4c1e-ad93-73b13744410b)
![Screenshot 2024-10-02 134814](https://github.com/user-attachments/assets/5a315754-9559-40f0-ba9e-da1bbbe87e07)
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 134903](https://github.com/user-attachments/assets/9af9ba0f-587f-4ec5-9229-50cb4486784f)
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 134937](https://github.com/user-attachments/assets/9dc36fca-b780-496c-8d9e-041cea41db37)
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 135008](https://github.com/user-attachments/assets/d52da87c-6a1d-43e1-a4d4-d8481b8b14d1)





### Adaptive Thresholding
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 135104](https://github.com/user-attachments/assets/7faaf1af-f5e6-467e-8312-a531d900240f)



### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-10-02 135550](https://github.com/user-attachments/assets/40951c9e-bfe5-497a-8a37-72013e3f3a8f)
![Screenshot 2024-10-02 135128](https://github.com/user-attachments/assets/e72117b5-8131-4bb7-bcb8-4dfa5698fab6)



## Result:

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
