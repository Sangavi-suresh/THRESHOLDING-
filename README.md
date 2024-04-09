# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

 ### Step1:
Import necessary packages

### Step2:
Read the image

### Step3:
If the read image is a color image, convert it into a grayscale image

### Step4:
perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's thresholding)

### Step5:
Display the Results


## Program
```
Developed By: SANGAVI SURESH
Register No: 212222230130
```
# Load the necessary packages

import cv2




# Read the Image and convert to grayscale

img = cv2.imread('cat.jpeg',-1)
cv2.imshow('original_image',img)
cv2.waitKey(0)
cv2.destroyAllWindows
gray =cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('gray_image',gray)
cv2.waitKey(0)
cv2.destroyAllWindows


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img6=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img8=cv2.threshold(gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

image =[thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,8):
    cv2.imshow('threshold_image',image[i])
    cv2.waitKey(0)
    cv2.destroyAllWindows



```
### Output

### Original Image

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/1540d0aa-b8a7-42e4-ab53-8e3432ed8919)


### Global Thresholding

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/d566dfe9-5c39-4019-8e1e-2b197548b9c3)

![274239738-c90055a5-652f-48b2-a508-3c21de9d3200](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/ea74b922-201e-43a5-8835-c120c64d741a)

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/3c8124c6-3166-4a80-a44b-3db7bcc680a9)

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/9765dc4a-726c-471e-9de9-53eedf126a14)

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/a355e56a-310f-4484-8e1b-c912c28e4672)

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/0c6293cc-779a-4f9b-b5cd-bc3243d7b270)

### Adaptive Thresholding

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/aa45b57e-b532-42ff-ae55-085e8859bc09)

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/46590eaa-ea65-4bf5-a356-3fa3260f6152)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/Sangavi-suresh/THRESHOLDING-/assets/118541861/30499f48-a638-4203-a3d6-f66a943b011c)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
