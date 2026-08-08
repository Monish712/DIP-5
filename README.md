## Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:** PAKANATI MONISH
- **Register Number:** 212224240109
  ```
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  ```
  img = cv2.imread("pspk.webp")
  img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  ```
  ```
  plt.imshow(img)
  plt.title("Original Image")
  plt.axis("off")
  plt.show()
  ```
  1. Averaging Filter
  ```
  avg = cv2.blur(img, (5,5))
  plt.imshow(avg)
  plt.title("Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
  2. Weighted Averaging Filter
  ```
  kernel = np.array([[1,2,1],
                   [2,4,2],
                   [1,2,1]], np.float32) / 16
  weighted = cv2.filter2D(img, -1, kernel)
  plt.imshow(weighted)
  plt.title("Weighted Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
3. Gaussian Filter
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
4. Median Filter
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
5. Laplacian Sharpening (Kernel)
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
6. Laplacian Operator
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

### Smoothing Filters

- Averaging filter produces blurred image

<img width="340" height="500" alt="image" src="https://github.com/user-attachments/assets/b09a4da7-043d-480e-95a3-ab28092a7937" />

<img width="361" height="520" alt="image" src="https://github.com/user-attachments/assets/6dbb92df-b3d1-4003-841d-fae2fec8e70d" />


  
- Weighted averaging provides smoother result with less distortion

 <img width="346" height="520" alt="image" src="https://github.com/user-attachments/assets/485e6d6d-e4ac-4553-802a-55b262309513" />


- Gaussian filter preserves edges better while reducing noise

<img width="347" height="506" alt="image" src="https://github.com/user-attachments/assets/3c683a7a-cbcd-4187-ad23-633bdda19f11" />

 

- Median filter removes salt-and-pepper noise effectively

<img width="350" height="505" alt="image" src="https://github.com/user-attachments/assets/a606a42b-9cb9-4d45-9fff-f209bec393ca" />

 


###  Sharpening Filters

- Laplacian kernel enhances edges and fine details

<img width="352" height="500" alt="image" src="https://github.com/user-attachments/assets/bf861df3-7938-4bf6-b225-5e5cae3fd9c6" />



- Laplacian operator detects edges clearly in grayscale

 
<img width="377" height="511" alt="image" src="https://github.com/user-attachments/assets/ce7e4383-b602-45a3-873a-45d360d54e77" />




---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
