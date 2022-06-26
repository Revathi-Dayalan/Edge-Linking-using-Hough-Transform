### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software required:
Anaconda - Python 3.7

### Algorithm:
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

### Output:
![REVA1](https://user-images.githubusercontent.com/96000574/175816240-4e642b43-e65b-420e-9b74-24e3c22ff109.png)
![REVA2](https://user-images.githubusercontent.com/96000574/175816249-54e20e7f-25ae-4fa1-b97b-33c551784a48.png)
![REVA3](https://user-images.githubusercontent.com/96000574/175816257-101bb3f9-5498-4178-ad51-528e457ade52.png)
