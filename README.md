# EX-6 EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:
Import all the necessary modules for the program.
Step2:
Load a image using imread() from cv2 module.
Step3:
Convert the image to grayscale
Step4:
Using Sobel operator from cv2,detect the edges of the image.
Step5:
Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## PROGRAM:
```
DEVELOPED BY: MOUNESH P
REGISTER NUMBER: 212222230084
```
### Import packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Load the image
```python
image = cv2.imread('cars.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
### Apply Sobel edge detector
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y) 
```
### Apply Laplacian edge detector
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
```
### Apply Canny edge detector
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
```
### Display results using Matplotlib
```python
plt.figure(figsize=(12, 12))
```
### Original Image
```python
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
### Sobel Edge Detection
```python
plt.subplot(2, 2, 2)
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
### Laplacian Edge Detection
```python
plt.subplot(2, 2, 3)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
### Canny Edge Detection
```python
plt.subplot(2, 2, 4)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
### Show all results
```python
plt.tight_layout()
plt.show()
```
## Output:
### ORIGINAL IMAGE:
![image](https://github.com/user-attachments/assets/36fd19b1-51e6-484d-9cb8-eb88b63233ba)

### SOBEL EDGE DETECTOR:
![image](https://github.com/user-attachments/assets/ce39faee-c1f6-454a-92af-6fc9a6449957)

### LAPLACIAN EDGE DETECTOR
![image](https://github.com/user-attachments/assets/4f1cfe26-420d-423a-9788-fb46ec891867)

### CANNY EDGE DETECTOR
![image](https://github.com/user-attachments/assets/33d0e566-b96b-49cf-af5f-0cec4f35a137)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
