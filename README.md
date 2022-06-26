### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software Required:
Anaconda - Python 3.7

### Algorithm:

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step 4:
Using Canny operator from cv2,detect the edges of the image.

### Step 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Program:
# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('fade.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)

plt.imshow(image1,cmap='gray')
plt.title('Input Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)


# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)

# Display the result
plt.title('Hough Lines')
plt.imshow(edges1,'gray')

# output:
![REVA1](https://user-images.githubusercontent.com/96000574/175815881-c3a75861-8587-467e-857f-8bc9ea56b7df.png)
![REVA2](https://user-images.githubusercontent.com/96000574/175815887-719686a5-0c31-415b-b912-9754f0864099.png)
![REVA3](https://user-images.githubusercontent.com/96000574/175815891-a26fcbb4-d086-4b97-a1fc-3f97ada37a0e.png)

