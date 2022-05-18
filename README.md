# Edge-Linking-using-Hough-Transform
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:

### Read image and convert it to grayscale image
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
from cv2 import cvtColor
image=cv2.imread("ir.jpg")
cv2.imshow("ORIGINAL",image)
#gray=cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)

plt.figure(1)
plt.subplot(1,2,1)
plt.imshow(image)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image)
plt.title('gray')
plt.axis('off')

```
### Find the edges in the image using canny detector and display
```python
edges = cv2.Canny(image, 120, 150)
plt.imshow(edges)
plt.title('EDGES')
plt.axis('off')
```
### Detect points that form a line using HoughLinesP
```python
lines=cv2.HoughLinesP(edges,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

```
### Draw lines on the image
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,0,205),2)
```
### Display the result
```python
plt.imshow(image)
plt.title('HOUGH')
plt.axis('off')

```
## Output

### Input image and grayscale image
![gray](https://user-images.githubusercontent.com/75236145/169021683-fc927300-ab88-43e3-8b33-f26e60c0933b.png)

### Canny Edge detector output
![edges](https://user-images.githubusercontent.com/75236145/169021706-7399cbb2-770d-411a-a95d-065b941febe5.png)

### Display the result of Hough transform
![th](https://user-images.githubusercontent.com/75236145/169021739-c9c39986-440f-47d5-9f8a-7bdaa7ae1536.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
