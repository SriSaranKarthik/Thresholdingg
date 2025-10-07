# EX(8):THRESHOLDING
## Name: K.SriSaran Karthik
## Reg no: 212224230275

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

## Image
<img width="292" height="192" alt="image" src="https://github.com/user-attachments/assets/0d06e558-4e21-4fc1-8460-1c9943e78748" />

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the necessary packages
# (Already done above by importing cv2, numpy, and matplotlib)

# Step 2: Read the Image and convert to grayscale
image = cv2.imread('MAx.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Display Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image, 
    255, 
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C, 
    cv2.THRESH_BINARY, 
    11, 
    2
)

# Step 5: Use Otsu's method to segment the image
_, otsu_thresholded = cv2.threshold(
    gray_image, 
    0, 
    255, 
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Display Global Thresholding Result
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Display Adaptive Thresholding Result
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Display Otsu's Method Result
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show all the results together
plt.tight_layout()
plt.show()
```
## Output
<img width="750" height="527" alt="image" src="https://github.com/user-attachments/assets/31ec7608-bcd0-4cc1-b1f0-85aa400c9229" />
