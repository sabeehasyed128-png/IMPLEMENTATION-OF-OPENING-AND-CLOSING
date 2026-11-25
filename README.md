# OPENING-AND-CLOSING-USING-OPENCV

## Aim

To implement Opening and Closing morphological operations using Python and OpenCV.

---

## Software Required

1. Anaconda – Python 3.7
2. Jupyter Notebook / VS Code
3. OpenCV (`cv2`)
4. NumPy
5. Matplotlib

---

## Developed By

- **Name:** SABEEHA PARVEEN K
- **Register No:** 212225230233

---

## ⚙️ Algorithm

### Step 1:
Import the necessary packages, including OpenCV, NumPy, and Matplotlib.

### Step 2:
Load the input image using `cv2.imread()`.

### Step 3:
Create a structuring element (kernel) of size 5 × 5 using `cv2.getStructuringElement()`.

### Step 4: Opening Operation

- Apply the Opening operation using `cv2.morphologyEx()`.
- Opening is performed by applying Erosion followed by Dilation.
- It helps remove small foreground noise and unwanted objects.

### Step 5: Closing Operation

- Apply the Closing operation using `cv2.morphologyEx()`.
- Closing is performed by applying Dilation followed by Erosion.
- It helps fill small holes and gaps in foreground objects.

### Step 6:
Convert the original, Opening, and Closing images from BGR to RGB format using `cv2.cvtColor()`.

### Step 7:
Display the original image, Opening result, and Closing result using Matplotlib.

---

## Program

```python
# Developed By: SABEEHA PARVEEN K 
# Register No: 212225230233

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')


# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)

# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')

# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Closing Operation")
plt.axis('off')
```

---

## Output

### 1. Original Input Image

<img width="511" height="472" alt="image" src="https://github.com/user-attachments/assets/46fee158-f040-4ba9-a7ad-f35ff8640f25" />


### 2. Opening Operation

<img width="527" height="472" alt="image" src="https://github.com/user-attachments/assets/5f8fc6f7-00bc-4de3-b890-0f0d89a43b0e" />


### 3. Closing Operation

<img width="507" height="466" alt="image" src="https://github.com/user-attachments/assets/d8a328bb-a4fe-4848-8438-78025ecc9f40" />


---

## Result

Thus, the Opening and Closing morphological operations were successfully implemented using Python and OpenCV. Opening helps remove small foreground noise, whereas Closing helps fill small holes and gaps in objects.
