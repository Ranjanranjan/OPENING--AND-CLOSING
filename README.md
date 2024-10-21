# EX-10:OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:Read the Image:
Load the input color image from a specified path.

### Step-2:Convert to Grayscale:
Transform the color image into a grayscale format for easier processing.

### Step-3:Edge Detection:
Apply an edge detection technique to identify the prominent edges in the grayscale image.

### Step-4:Create Structuring Element:
Define a kernel (structuring element) for use in morphological operations, typically a matrix of ones.

### Step-6:Morphological Operations:
Perform morphological operations:<br>
Opening: Remove small objects from the edges to clean up the image.<br>
Closing: Fill small holes in the detected edges to enhance the structure.

### Step-7:Display Results:
Show the original grayscale image, along with the results of the opening and closing operations for visual comparison.

## Program:


## Create the structuring element
```python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("/content/uiop.jpg")  
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10, 5))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
<img width="504" alt="Screenshot 2024-10-21 at 10 59 48 AM" src="https://github.com/user-attachments/assets/d30bfaff-74eb-411e-899b-3f638092af44">

## Use Opening operation
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("/content/uiop.jpg")  
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")
```
<img width="427" alt="Screenshot 2024-10-21 at 11 00 08 AM" src="https://github.com/user-attachments/assets/1fcbed12-85ee-47fe-9564-685deb030993">


## Use Closing Operation
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("/content/uiop.jpg")  
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")
```
<img width="430" alt="Screenshot 2024-10-21 at 11 00 28 AM" src="https://github.com/user-attachments/assets/063761fa-80f0-4539-900e-b36a60edc009">

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
