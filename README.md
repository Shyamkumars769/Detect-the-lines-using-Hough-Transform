#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

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
image = cv2.imread('Qn_7_.jpg')  # Replace with your image path
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
plt.figure(figsize=(10,5))

# Display the original image
plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')

# Display the grayscale image
plt.subplot(1, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.show()
```

---

###  Step 5: Thresholding

```python
# Apply thresholding
threshold = 50
_, threshold_image = cv2.threshold(gray_image, threshold, 255, cv2.THRESH_BINARY)
```

---

###  Step 6: Region of Interest (ROI)

```python
# ROI masking already provided
# (Do not modify)
```

---

### Step 7: Edge Detection (Canny)

```python
# Perform Edge Detection
edges = cv2.Canny(gray_image, 50, 150)
```

---

###  Step 8: Gaussian Blur

```python
# Apply Gaussian Blur
blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)
```

---

###  Step 9: Hough Transform

```python
# Detect lines using Hough Transform
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

# Draw the detected lines on the original image
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

---

### Step 10: Lane Detection Logic

```python
# Already implemented
# (Do not modify)
```

---

##  Expected Output

* Original image
* Grayscale image
* Thresholded image
* ROI masked image
* Edge detected image
* Smoothed image
* Detected lines
* Final lane detection output

---

##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs

---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---

##  Developed By

* **Name:** Shyam Kumar S
* **Register No:** 212224040315
