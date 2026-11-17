# EX. No: 6 – EDGE DETECTION
### Developed By : HARISH KUMAR S
### Register Number : 212224230091
### Aim :
To implement various edge detection techniques using Python and OpenCV to identify and highlight the edges and boundaries of objects in an image.
### Requirements :
Hardware Requirements:
- Computer or Laptop
- Minimum 4 GB RAM
Software Requirements:
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib
### Procedure :
1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using cv2.imread().
3. Convert the original image into grayscale using cv2.cvtColor().
4. Display the original image using Matplotlib.
5. Apply the Sobel Edge Detection method in X and Y directions.
6. Combine both Sobel directions using cv2.magnitude().
7. Apply the Laplacian Edge Detection method to identify rapid intensity changes.
8. Apply the Canny Edge Detection method using threshold values 50 and 150.
9. Display the detected edges using Matplotlib.

### Program : 
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('ex.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('on')
```
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('on')
```
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('on')
```
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('on')
```

### Output : 

<img width="352" height="497" alt="Screenshot 2026-11-17 235505" src="https://github.com/user-attachments/assets/82959395-f9ad-4224-ba1a-1318948cfc4e" />


<img width="362" height="500" alt="Screenshot 2026-11-17 235514" src="https://github.com/user-attachments/assets/c108a1d6-6a39-4b50-9dd0-789e0dbbd20a" />



<img width="358" height="500" alt="Screenshot 2026-11-17 235528" src="https://github.com/user-attachments/assets/f20eb04e-27ec-4aa8-926c-5aa03483b67c" />


<img width="357" height="502" alt="Screenshot 2026-11-17 235541" src="https://github.com/user-attachments/assets/534ea41f-7415-4547-a846-e3649098d944" />












### Result :
Thus, various edge detection techniques such as Sobel, Laplacian, and Canny were successfully implemented using Python and OpenCV. The edges and boundaries of objects in the input image were identified and displayed successfully.
