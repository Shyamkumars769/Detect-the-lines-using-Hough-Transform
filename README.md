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
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')

# Display the grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```

---

###  Step 5: Canny edge operator

```python
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---

---

###  Step 6: Hough Transform

```python
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line

    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

# Display the image
plt.figure(figsize=(12, 8))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Detected Lines")
plt.axis('off')
plt.show()
```

---

##  Expected Output

* Original image
* Grayscale image
* Canny Edge Detection
* Edge detected image
* Detected lines
* Final lane detection output

---

## OUTPUT:

Original image
<img width="1290" height="860" alt="Qn_7_" src="https://github.com/user-attachments/assets/918d60de-5c0b-4207-8155-75545ad0d0e8" />

Grayscale image
<img width="636" height="461" alt="grayscale image" src="https://github.com/user-attachments/assets/173ad5ee-ff3b-49b1-959f-b97c8f0b44d9" />

Detected lines
<img width="637" height="455" alt="hou" src="https://github.com/user-attachments/assets/2f9e76fa-1b8f-4dbe-96d1-4d5e2f15d1ae" />


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
