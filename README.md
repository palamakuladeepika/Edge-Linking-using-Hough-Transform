# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules.

### Step2:
Import the image to operate on.

### Step3:
Convert the imported image from BGR to GRAYSCALE.

### Step4:
Find the edges using canny edge detector and display the image.

### Step5:
Detect the points that form a line using hough transform.

### Step6:
Draw the lines on the image

### Step7:
Display the output

### Step8:
End the program.

## Program:
```Python
Developed by: Palamakula Deepika
RegisterNumber:  212221240035
# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(smoothImage,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(image,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(image)
plt.show()


```
## Output

### Input image and grayscale image
![dorg](https://user-images.githubusercontent.com/94154679/171150712-4f8b903a-9768-4044-bdbc-deb151d69887.png)

![dgray](https://user-images.githubusercontent.com/94154679/171150700-a4529134-5819-4558-8661-ffc29571c705.png)

<br>

### Canny Edge detector output
![dedge](https://user-images.githubusercontent.com/94154679/171150807-d4216528-5965-42b7-8fdc-d8abc40d8b98.png)

<br>


### Display the result of Hough transform
![dhough](https://user-images.githubusercontent.com/94154679/171150836-8aec66ae-ec5b-43af-87df-6cef3609858c.png)

<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
