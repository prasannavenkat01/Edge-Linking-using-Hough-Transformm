# EXP:07 Edge-Linking-using-Hough-Transformm
# NAME: PRASANNA V
# REF NO: 212223240123
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
## program:
```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read your uploaded image
image = cv2.imread('/content/WhatsApp Image 2025-11-10 at 09.26.30.jpeg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Detect edges using Canny
edges = cv2.Canny(gray_image, 50, 150)

# Detect lines using Hough Transform
lines = cv2.HoughLinesP(edges, 1, np.pi/180, 100, minLineLength=50, maxLineGap=10)

# Draw the detected lines
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

# Show all results
plt.figure(figsize=(12,8))

plt.subplot(1,3,1)
plt.imshow(cv2.cvtColor(gray_image, cv2.COLOR_BGR2RGB))
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1,3,2)
plt.imshow(edges, cmap='gray')
plt.title('Edges (Canny)')
plt.axis('off')

plt.subplot(1,3,3)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Lines Detected (Hough)')
plt.axis('off')

plt.show()

```
## Output

### Input image and grayscale image
<img width="291" height="394" alt="image" src="https://github.com/user-attachments/assets/5c567f20-fc12-473e-a532-a61d685c7475" />

<img width="183" height="238" alt="image" src="https://github.com/user-attachments/assets/16ffba99-99db-4c89-8e70-55d1a2cccf71" />


### Canny Edge detector output


<img width="307" height="402" alt="image" src="https://github.com/user-attachments/assets/581c3a14-48fc-4520-a748-fa0c06d539ef" />


### Display the result of Hough transform


<img width="303" height="399" alt="image" src="https://github.com/user-attachments/assets/c58d24cb-c9e2-41a9-8547-8136040543dd" />
