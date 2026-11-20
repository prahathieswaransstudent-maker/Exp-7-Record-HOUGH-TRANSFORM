#  Lane Detection

### Developed By 
#### Name : Prahathieswaran S
#### Register No : 212225240107

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```python
# Read the image using OpenCV

# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('profile.png')  # Replace 'image.jpg' with your image path
```

---

###  Step 3: Convert to Grayscale

```python
# Convert to grayscale.
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 4: Display Images

```python

# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

<img width="266" height="410" alt="image" src="https://github.com/user-attachments/assets/d1c44625-9745-4083-a21f-ad3947e77576" />

```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

<img width="266" height="410" alt="image" src="https://github.com/user-attachments/assets/22795ff0-893c-4db0-8afb-0b085cb8ed25" />


```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 7: Edge Detection (Canny)

```python
# Perform Edge Detection

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

<img width="266" height="410" alt="image" src="https://github.com/user-attachments/assets/3742070a-61a0-432a-9bc2-1b93eba0d47c" />

---


###  Step 9: Hough Transform

```python
# Detect lines using Hough Transform

# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image

# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)


# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates

# The lines variable contains the endpoints of the detected lines

for line in lines:
    x1, y1, x2, y2 = line.flatten()  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2

# Display the result of Hough Transform (Image with lines)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```

<img width="266" height="410" alt="image" src="https://github.com/user-attachments/assets/0bad1895-8c45-4778-8903-f1327c95426b" />

---





## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---

