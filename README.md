# Ex 08: image-thresholding-opencv
# Aim
To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

Global Thresholding Adaptive Thresholding Otsu's Thresholding

# Software Used
Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib

# Algorithm
Step 1:Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:Load the input image using OpenCV.

Step 3:Convert the input image into grayscale format.

Step 4: Global Thresholding Select a fixed threshold value. Display the thresholded image.

Step 5: Adaptive Thresholding Compute threshold values for small regions of the image. Apply Adaptive Mean Thresholding. Apply Adaptive Gaussian Thresholding. Display the segmented images.

Step 6: Otsu's Thresholding Automatically determine the optimal threshold value. Apply Otsu's thresholding technique. Display the segmented image.

Step 7: Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

# Program

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('pic8')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
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
# Output
<img width="255" height="182" alt="image" src="https://github.com/user-attachments/assets/7f94701d-169a-457c-9ce8-9e8cc759ea97" />
<img width="640" height="452" alt="image" src="https://github.com/user-attachments/assets/7c4db8a0-623c-4c48-9be2-7732d221ef89" />


# Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
