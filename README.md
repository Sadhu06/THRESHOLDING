# THRESHOLDING

## NAME : SADHANA S
## REGISTER NUMBER : 212224230234

## Aim

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Used

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm

## Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

## Step 2:
Load the input image using OpenCV.

## Step 3:
Convert the input image into grayscale format.

## Step 4: Global Thresholding
Select a fixed threshold value.

Apply thresholding to separate foreground and background pixels.

Display the thresholded image.

## Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.

Apply Adaptive Mean Thresholding.

Apply Adaptive Gaussian Thresholding.

Display the segmented images.

## Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.

Apply Otsu's thresholding technique.

Display the segmented image.

## Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load Original Image
image = cv2.imread(r"C:\Users\admin\Downloads\mypic.jpeg")

# Convert to Grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Global Thresholding
threshold_value = 127
ret, thresholded_image = cv2.threshold(gray_image, threshold_value, 255, cv2.THRESH_BINARY)

# Display Global Thresholded Image
plt.imshow(thresholded_image, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
plt.show()

# Adaptive Mean Thresholding
adaptive_mean = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)

# Adaptive Gaussian Thresholding
adaptive_gaussian = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Display Adaptive Thresholding Results
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(gray_image, cmap='gray')
plt.title("Original Grayscale")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(adaptive_mean, cmap='gray')
plt.title("Adaptive Mean Thresholding")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title("Adaptive Gaussian Thresholding")
plt.axis('off')

plt.tight_layout()
plt.show()

# Otsu's Thresholding
otsu_threshold, otsu_image = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display Otsu's Thresholding
plt.imshow(otsu_image, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')
plt.show()

print("Optimal Otsu Threshold Value:", otsu_threshold)
```

## Output

## Original Grayscale Image

<img width="317" height="519" alt="image" src="https://github.com/user-attachments/assets/1be36932-1c6b-4937-94fd-19282fcfd936" />

## Global Thresholding

<img width="337" height="527" alt="image" src="https://github.com/user-attachments/assets/2522d775-7aea-4e51-81c5-3483d67408bb" />

## Adaptive Thresholding

<img width="357" height="521" alt="image" src="https://github.com/user-attachments/assets/105e8fb0-6875-42ed-94bf-f8776a84c494" />

<img width="356" height="524" alt="image" src="https://github.com/user-attachments/assets/29aa86e6-772b-444e-863b-b86f02054f3d" />

## Otsu's Thresholding

<img width="389" height="567" alt="image" src="https://github.com/user-attachments/assets/b1d168a2-072f-45f9-85f4-4a842f50538e" />


## Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
