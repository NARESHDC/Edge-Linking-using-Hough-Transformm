# Edge-Linking-using-Hough-Transformm
# Name: NARESH.M
# Register No: 212223220064
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
## Output

### Input image and grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread('nar.png', cv2.IMREAD_GRAYSCALE)
img_color = cv2.imread('nar.png', cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray, cv2.COLOR_GRAY2RGB)

gray = cv2.GaussianBlur(gray, (3, 3), 0)

plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray_rgb, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()

```
<img width="1671" height="893" alt="{0EE4665C-D083-4D10-AAFA-B58F9D93C046}" src="https://github.com/user-attachments/assets/a8ca4e0f-1fee-4b95-b0d3-3a838188309c" />


### Canny Edge detector output
```
canny = cv2.Canny(gray, 120, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

```
<img width="743" height="890" alt="{3B87AE39-2B38-4CCC-B852-EAD7619F5D17}" src="https://github.com/user-attachments/assets/426da88b-05b9-4477-b89a-5d743a0b2de7" />



### Display the result of Hough transform
```
lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```
<img width="755" height="897" alt="{E576F68F-10C5-4BA5-9D4A-4602D524472E}" src="https://github.com/user-attachments/assets/5c1c7969-6777-4643-b9c6-7e4633b99529" />

### Result:
Thus, the image has been successfully converted.
