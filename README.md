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

# Step 2: Read the image and convert to grayscale
image = cv2.imread(r"C:\Users\admin\Downloads\mypic.jpeg")
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

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

## Output

## Original Image

<img width="278" height="316" alt="image" src="https://github.com/user-attachments/assets/aca8619b-c18c-4cba-a3e2-2582a871a3ac" />


## Global Thresholding

<img width="247" height="294" alt="image" src="https://github.com/user-attachments/assets/11e4c502-730d-429e-864e-d0336b762882" />


## Adaptive Thresholding

<img width="317" height="320" alt="image" src="https://github.com/user-attachments/assets/48c80afe-8700-4830-8da6-8a6dbaa95869" />


## Otsu's Thresholding

<img width="176" height="311" alt="image" src="https://github.com/user-attachments/assets/1cac28d0-08a8-48a0-8022-de0ccd4e017a" />



## Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
