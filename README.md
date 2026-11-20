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
## Name: SHRAVANI M
## Register No: 212224230263  
```.PY

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image in grayscale
img = cv2.imread('photo.jpeg', cv2.IMREAD_GRAYSCALE)

# Display Original Image
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Display Original Histogram
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

# Histogram Equalization
img_eq = cv2.equalizeHist(img)

# Display Equalized Histogram
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

# Display Equalized Image
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Read Color Image
img = cv2.imread('pic.jpeg', cv2.IMREAD_COLOR)

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Apply Histogram Equalization to V channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display Equalized Image
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

# Display Histogram Equalized
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

# Display Original and Equalized Images
plt.figure(figsize=(20, 10))

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()

# Display Original and Equalized Histograms
plt.figure(figsize=[15, 4])

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')

plt.show()

```
##  Output

### Grayscale Histogram Equalization
<img width="482" height="445" alt="image" src="https://github.com/user-attachments/assets/879f157f-f75e-418f-a97a-a7dc6f7d0b10" />
<img width="653" height="448" alt="image" src="https://github.com/user-attachments/assets/d7bdec3c-7fdc-4ce2-8fc3-4e2c08de318f" />
<img width="656" height="467" alt="image" src="https://github.com/user-attachments/assets/d9b8c746-7e5d-4a44-88c7-81ab7ae5c1b7" />
<img width="527" height="442" alt="image" src="https://github.com/user-attachments/assets/dcad3f0e-d225-4bb3-b719-12e20bdcfba5" />

### Color Image Histogram Equalization
<img width="487" height="437" alt="image" src="https://github.com/user-attachments/assets/c447c3d3-29e1-4a26-a4f5-5715dbfc7a31" />
<img width="792" height="447" alt="image" src="https://github.com/user-attachments/assets/49012363-e73e-46a7-9961-dcc85438b0b1" />
<img width="1106" height="387" alt="image" src="https://github.com/user-attachments/assets/0479e289-b8a9-443f-b3cb-809f696be01b" />

<img width="1102" height="371" alt="image" src="https://github.com/user-attachments/assets/c75bce36-6f56-41bc-b97d-6caa2360be09" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
