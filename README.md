# EXP-3-Record-Histogram-processing

Aim: To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image Plot histogram of the grayscale image Apply histogram equalization on grayscale image Read and display a color image Plot histogram of B, G, R channels Convert image to HSV color space Apply histogram equalization on the Value (V) channel Convert the enhanced image back to BGR format Display original and enhanced images with histograms Software Used: Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib Algorithm: Step 1: Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2: Read the image parrot.jpg in grayscale format.

Step 3: Display the grayscale image and plot its histogram.

Step 4: Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5: Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6: Read the same image in color format.

Step 7: Split the image into B, G, R channels and plot their histograms.

Step 8: Convert the image from BGR to HSV color space.

Step 9: Apply histogram equalization on the V (Value) channel.

Step 10: Merge the channels and convert the image back to BGR format.

Step 11: Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

Developed By: Name: MOHANA K.V.S.L

Register No: 21222420093

Program:

ORIGINAL IMAGE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
img = cv2.imread('mona.png', cv2.IMREAD_GRAYSCALE)
```
```
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
Equalized Histogram
```
img_eq = cv2.equalizeHist(img)
```
```
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```


```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
```
```
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```
Text(0.5, 1.0, 'Equalized Histogram')
```
```
img = cv2.imread('mona.png', cv2.IMREAD_COLOR)
```
```
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
Histogram Equalized

```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```






Output: 

ORIGINAL IMAGE:

<img width="497" height="568" alt="image" src="https://github.com/user-attachments/assets/4d839bf2-8f1f-457f-89f5-28b1a0598cf3" />

<img width="749" height="563" alt="image" src="https://github.com/user-attachments/assets/8a889a03-5c2a-4d2b-8625-f70d1682b7a8" />



Equalised Histogram:

<img width="453" height="532" alt="image" src="https://github.com/user-attachments/assets/eeb868fd-11f7-4682-b387-86cbea96097e" />

<img width="752" height="538" alt="image" src="https://github.com/user-attachments/assets/05682049-edb4-4e13-9926-6ac4439e942e" />



Equalized Image:

<img width="431" height="540" alt="image" src="https://github.com/user-attachments/assets/300b7898-5e93-44e8-958a-ed6e1907c0cc" />

<img width="464" height="550" alt="image" src="https://github.com/user-attachments/assets/eafdc4e7-21e3-47f9-8d25-d099a5683a1d" />




Histogram Equalization of Grayscale Image:

<img width="1286" height="479" alt="image" src="https://github.com/user-attachments/assets/8ad25750-f4ec-4b04-8884-ce527b47ca6e" />

<img width="1301" height="423" alt="image" src="https://github.com/user-attachments/assets/a85c34cd-3edb-424c-961c-8ef6ecb50266" />



