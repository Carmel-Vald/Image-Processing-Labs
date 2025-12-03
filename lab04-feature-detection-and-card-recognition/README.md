# Lab 4 – Feature Detection, Color Segmentation & Shape Matching

This lab explores advanced feature-extraction techniques in digital image processing.
The exercises focus on edge detection, Hough-based line detection, color-based
segmentation, connected-component analysis, Structural Similarity (SSIM) matching,
and handling noisy images with denoising filters.

## Goals

- Convert RGB images to grayscale for edge detection tasks.
- Compute adaptive thresholds and apply the **Canny** edge detector.
- Detect straight lines using the **Hough transform** and visualize selected lines.
- Perform **color segmentation** using red/green channel masks for object detection.
- Extract connected components and draw bounding boxes around detected cards.
- Compare shapes using the **SSIM metric** and identify the correct matching card.
- Add synthetic noise and improve robustness using **median** and **Gaussian** filters.

## Repository Contents

- **`lab4.ipynb`**  
  Main Python notebook implementing all Lab 4 tasks.

## Main Experiments

### 1. Canny Edge Detection & Hough Transform
- Load an image and convert it to grayscale.
- Compute the 15% lower and upper gray-level thresholds for Canny.
- Detect edges and apply the **Hough transform** to find straight lines.
- Select the strongest detected lines and overlay them on the original image.

### 2. Color-Based Segmentation (Red & Green Cards)
- Load an RGB image and normalize channels to \[0–1\].
- Compute channel ratios (e.g., S = R+G+B, g = G/S, r = R/S).
- Build masks for **red** and **green** regions using tuned thresholds.
- Extract connected components and draw purple bounding boxes around detected cards.

### 3. Shape Matching Using SSIM
- Compare candidate card patches to the reference card.
- Use the **SSIM metric** to find the most similar shape  
  (score = 1.0 indicates a perfect match).
- Discuss behavior when shapes differ in structure or brightness.

### 4. Noise Addition & Denoising
- Add heavy synthetic noise to the color image.
- Show that color masks fail under noise.
- Apply:
  - **3×3 median filter**  
  - **Gaussian filter (σ = 1)**
- Re-run the segmentation algorithm from Section 2 to show improved detection.

## How to Run

1. Open **`lab4.ipynb`** in Jupyter Notebook or VS Code.
2. Install required libraries:

   ```bash
   pip install numpy matplotlib opencv-python scikit-image
   ```

---
