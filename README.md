# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
### Name: pravin kumar G
### Register number: 212222230109
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('chess.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)

# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)


# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))

# Input Image and Grayscale Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

# Canny Edge Detection Output
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')

# Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```

## Output

### Input image and grayscale image

![image](https://github.com/user-attachments/assets/2c836a68-4960-40b5-bba6-95fb608cc9a8)

![image](https://github.com/user-attachments/assets/6a9066fa-9423-4d3e-ab65-0b7789a01d87)



### Canny Edge detector output
![image](https://github.com/user-attachments/assets/479b38ec-73f8-4fa0-9b72-df5b8dfdec14)



### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/acc9200a-71a9-45b8-aa67-30716aa7462e)


## Result:
Thus, the program to detect the lines using Hough Transform implemented successfully.
