# EX NO-8
THRESHOLDING

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7

OpenCV

## Algorithm
Step1:
Load the necessary packages.

Step2:

Read the Image and convert to grayscale.

Step3:

Use Global thresholding to segment the image.

Step4:

Use Adaptive thresholding to segment the image.

Step5:

Use Otsu's method to segment the image and display the results.

## Program
### Developed By : Kiruba RC
### Register Number : 212224230125

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
image = cv2.imread('Qn8_thresholding.tif')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```
```python
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
<img width="319" height="300" alt="image" src="https://github.com/user-attachments/assets/04e84d41-680d-4049-86fa-0eb26196d0bd" />

```python
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```
```python
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```
```python
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
```python
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
<img width="345" height="283" alt="image" src="https://github.com/user-attachments/assets/a2114f9c-6c0a-4e08-a79e-8443a29307e2" />

<img width="306" height="304" alt="image" src="https://github.com/user-attachments/assets/bc0f0be8-49a5-4cb3-8890-009d85fe547c" />

<img width="382" height="291" alt="image" src="https://github.com/user-attachments/assets/6327e9b2-2fb5-4b1f-8c1a-ac9b28d4ca52" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.



