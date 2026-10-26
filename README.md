# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** chandru V

**Register Number:** 212224230043

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r"C:\Users\admin\Downloads\dip_sample_image.png", cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread(r"C:\Users\admin\Downloads\dip_sample_image.png", cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="480" height="542" alt="image" src="https://github.com/user-attachments/assets/e968be69-36ca-456c-b018-eb388bdd2ca2" />


### Input Grayscale Image Range
<img width="732" height="546" alt="image" src="https://github.com/user-attachments/assets/6f59712f-ae85-49e5-9ef7-cc3d31e34a26" />


### Input Grayscale Image Equalized Histogram
<img width="740" height="596" alt="image" src="https://github.com/user-attachments/assets/79aa092f-0eef-49da-a974-b5640ac2762c" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="458" height="538" alt="image" src="https://github.com/user-attachments/assets/40f9fc02-bfa4-4dea-af86-7dbe0b456db4" />


### Equalized Image

<img width="513" height="547" alt="image" src="https://github.com/user-attachments/assets/76aaa3c1-c12e-4284-a355-30660366e7ce" />


### Equalized Histogram
<img width="755" height="545" alt="image" src="https://github.com/user-attachments/assets/f49cf124-5a8c-4b7e-8aef-e6a08be50291" />


### Final Output of Original Image and Equalized 
<img width="811" height="297" alt="image" src="https://github.com/user-attachments/assets/b169d0dd-08c6-4a7f-ad8d-910f42f4f202" />



### Final Output of Original Image and its Histogram Equalized
<img width="778" height="312" alt="image" src="https://github.com/user-attachments/assets/880984ee-8038-434a-83cf-b0eed86dd059" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
