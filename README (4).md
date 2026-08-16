# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** VEDHA M

### Register No:212225230292  
```
# 1. Import the required libraries and read the grayscale image.
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# 2. Plot the histogram of the grayscale image.
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()

# 3. Apply histogram equalization.
img_eq = cv2.equalizeHist(img)

# 4. Display the histogram of the equalized image.
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()

# 5. Display the equalized grayscale image.
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

# 6. Read the image in color mode and convert to HSV.
img = cv2.imread('parrot.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# 7. Apply histogram equalization to the V channel.
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# 8. Convert the enhanced HSV image back to BGR.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# 9. Display the original and equalized color images.
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()

# 10. Display the original and equalized images along with their histograms.
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```
##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
- <img width="771" height="510" alt="image" src="https://github.com/user-attachments/assets/b4b08552-8f14-4b6a-b25a-151e25307b99" />
 
- Histogram of original grayscale image is plotted
-<img width="897" height="387" alt="image" src="https://github.com/user-attachments/assets/292ca9c0-9078-4b62-9101-4baab42c64ca" />


- Enhanced image after histogram equalization is displayed
- <img width="696" height="472" alt="image" src="https://github.com/user-attachments/assets/9903a53b-2b73-447f-9699-f9b670e12b48" />
 
- Histogram of enhanced grayscale image shows improved contrast
-    <img width="888" height="348" alt="image" src="https://github.com/user-attachments/assets/a9ed8575-6b93-45db-839f-c893a300bc83" />

### Color Image Histogram Equalization

- Original color image is displayed
- <img width="658" height="466" alt="image" src="https://github.com/user-attachments/assets/5a94141b-7f1a-4fa3-a2a8-20be2dd8952d" />
 
- Histogram of B, G, R channels is plotted
- <img width="883" height="473" alt="image" src="https://github.com/user-attachments/assets/423b2026-7c7f-4b58-916c-a1377d820909" />
 
- Enhanced image after HSV-based equalization is displayed
-  <img width="886" height="382" alt="image" src="https://github.com/user-attachments/assets/bdc7e945-0416-468e-b4cf-0da0341caf2c" />

- Histogram of enhanced image shows better intensity distribution  
<img width="870" height="345" alt="image" src="https://github.com/user-attachments/assets/3cfd5f10-9ae3-4732-8129-663fb7befc48" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
