# Exp-10--Record-IMPLEMENTATION-OF-OPENING-AND-CLOSING

# EXP10-Opening and Closing Operations Using OpenCV
# NAME :KARANKUMAR K
# REG NO : 212225040171
## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create binary image
img = np.zeros((300, 500), dtype=np.uint8)

# Draw white rectangle
cv2.rectangle(img, (100, 80), (350, 220), 255, -1)

# Add white noise
cv2.circle(img, (50, 50), 8, 255, -1)
cv2.circle(img, (400, 250), 8, 255, -1)

# Add black holes
cv2.circle(img, (150, 130), 10, 0, -1)
cv2.circle(img, (250, 170), 10, 0, -1)

# Create kernel
kernel = np.ones((15, 15), np.uint8)

# Opening
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

# Closing
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

# Display results
plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap='gray')
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title("Opening")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title("Closing")
plt.axis('off')

plt.show()

```

## Output


### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.

### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.

### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.

## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV.
