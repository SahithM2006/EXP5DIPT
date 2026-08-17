# IMAGE SMOOTHING AND SHARPENING USING OPENCV

## AIM

To write a Python program using OpenCV to apply different smoothing filters such as Averaging, Weighted Averaging, Gaussian, and Median filters, and sharpening filters such as Laplacian Kernel and Laplacian Operator for image enhancement.

## SOFTWARE USED

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

## ALGORITHM

### Step 1: Import Libraries

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2: Read the Image

Read the input image using `cv2.imread()`.

### Step 3: Convert Image

Convert the image from BGR to RGB format using `cv2.cvtColor()` for proper display.

### Step 4: Averaging Filter

* Create an averaging kernel.
* Apply the filter using `cv2.filter2D()`.
* Display the original and filtered images.

### Step 5: Weighted Averaging Filter

* Create a weighted averaging kernel.
* Apply it using `cv2.filter2D()`.
* Display the result.

### Step 6: Gaussian Filter

* Apply Gaussian smoothing using `cv2.GaussianBlur()`.
* Display the original and Gaussian filtered images.

### Step 7: Median Filter

* Apply median filtering using `cv2.medianBlur()`.
* Display the result.

### Step 8: Laplacian Sharpening Using Kernel

* Create a Laplacian sharpening kernel.
* Apply it using `cv2.filter2D()`.
* Display the sharpened image.

### Step 9: Laplacian Operator

* Convert the image to grayscale.
* Apply the Laplacian operator using `cv2.Laplacian()`.
* Display the detected edges.

### Step 10: Display Results

Display the original image and all filtered results for comparison.

# PROGRAM

### Developed By

**Name:** KAYALVIZHI.V
**Register No:** 212225040182

---

## 1. Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("mk.jpeg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11, 11), np.float32) / 121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")

plt.show()
```

**Output:** Original Image and Average Filter Image

---
<img width="837" height="257" alt="image" src="https://github.com/user-attachments/assets/fecece87-8b3f-4bbb-89e2-fcbab4a946c8" />

## 2. Using Weighted Averaging Filter

```python
kernel1 = np.array([
    [1, 2, 1],
    [2, 4, 2],
    [1, 2, 1]
]) / 16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")

plt.show()
```

**Output:** Original Image and Weighted Average Filter Image

---
<img width="714" height="224" alt="image" src="https://github.com/user-attachments/assets/bb02e61c-8bff-4e54-be2f-0c6d803b9f67" />

## 3. Using Gaussian Filter

```python
gaussian_blur = cv2.GaussianBlur(image2, (33, 33), 0)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")

plt.show()
```

**Output:** Original Image and Gaussian Blurred Image

---
<img width="709" height="206" alt="image" src="https://github.com/user-attachments/assets/51c5c784-971e-4766-b5d9-61a5e93b8825" />

## 4. Using Median Filter

```python
median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")

plt.show()
```

**Output:** Original Image and Median Filtered Image

---
<img width="711" height="197" alt="image" src="https://github.com/user-attachments/assets/6f0771cc-d933-4ddc-9c76-78956e5f71a9" />

## 5. Using Laplacian Sharpening Kernel

```python
kernel2 = np.array([
    [0, -1, 0],
    [-1, 5, -1],
    [0, -1, 0]
])

sharpened = cv2.filter2D(image2, -1, kernel2)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(sharpened)
plt.title("Laplacian Sharpened Image")
plt.axis("off")

plt.show()
```

**Output:** Original Image and Laplacian Sharpened Image

---
<img width="681" height="404" alt="image" src="https://github.com/user-attachments/assets/6e0e0ac9-61d2-40f5-b77f-b26e3b4ccc11" />

## 6. Using Laplacian Operator

```python
gray = cv2.cvtColor(image1, cv2.COLOR_BGR2GRAY)

laplacian = cv2.Laplacian(gray, cv2.CV_64F)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(abs(laplacian), cmap="gray")
plt.title("Laplacian Operator")
plt.axis("off")

plt.show()
```

**Output:** Grayscale Image and Laplacian Edge Detection Image
<img width="663" height="382" alt="image" src="https://github.com/user-attachments/assets/dd3a4870-f856-4622-883d-46bc4a9ac96c" />

# OUTPUT

## Smoothing Filters

### Averaging Filter

Produces a blurred image by averaging neighboring pixels.

### Weighted Averaging Filter

Produces a smoother image by giving different weights to neighboring pixels.

### Gaussian Filter

Reduces noise while preserving image structures relatively well.

### Median Filter

Effectively reduces salt-and-pepper noise while preserving edges.

## Sharpening Filters

### Laplacian Sharpening Kernel

Enhances edges and fine details in the image.

### Laplacian Operator

Detects edges and fine intensity changes in the grayscale image.

# RESULT

Thus, different **smoothing and sharpening filters** were successfully implemented using OpenCV. Smoothing filters reduce noise and blur the image, while sharpening filters enhance edges and fine details for improved image analysis and feature extraction.
