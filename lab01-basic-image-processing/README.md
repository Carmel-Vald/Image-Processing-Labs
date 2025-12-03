# Lab 1 – Basic Image Processing & Thermal Imaging

This lab introduces fundamental tools in digital image processing using Python.
The experiments are based on visible-light and thermal images and cover dynamic
range, histograms, enhancement, edge detection, morphology, region properties,
and Hough-based line detection.

## Goals

- Acquire visible and thermal images with a FLIR XT8-E camera.
- Understand digital image representation, dynamic range and quantization.
- Analyze and manipulate image histograms (contrast, brightness, gamma, equalization).
- Apply spatial filters and edge detectors (Sobel, LoG, Canny).
- Use thresholding and morphological operations to segment objects.
- Extract region properties and use them for basic classification.
- Detect straight lines using the Hough transform.

## Repository Contents

- **`lab1.ipynb`**  
  Main Python notebook implementing all Lab 1 tasks.

- **`lab1.pdf`**  
  Full lab report with figures, explanations, and conclusions.

- `lab01-basic-image-processing/notebooks/`  
  (currently optional — placeholder for additional notebooks if needed)

## Main Experiments

### 1. Image Acquisition
- Capture three visible-light images and three thermal images of the same scene.
- Compare visual vs thermal representations and how intensity relates to temperature.

### 2. Dynamic Range & Histograms
- Inspect min, max, and mean intensity of grayscale images.
- Plot intensity profiles along rows/columns and explain how they relate to content.
- Add Gaussian noise and observe histogram spreading and variance changes.
- Compare histograms of visible-light and thermal images (8-bit vs 12-bit sensors).

### 3. Histogram-Based Enhancement
- Apply contrast stretching and brightness adjustments.
- Perform histogram equalization and examine histogram uniformity.
- Use gamma correction to improve low-contrast images and compare different γ values.

### 4. Edge Detection
- Apply Sobel, LoG, and Canny edge detectors with varying parameters.
- Discuss noise sensitivity, edge sharpness, and parameter selection.
- Compare edge maps in visible vs thermal images and explain differences.

### 5. Thresholding & Morphology
- Perform global thresholding on tools and rice images.
- Use erosion/dilation to remove noise and recover main objects.
- Perform background estimation + subtraction to improve segmentation quality.

### 6. Region Properties & Classification
- Label connected components and compute region measurements:
  area, convex area, eccentricity, solidity, axis lengths, perimeter.
- Classify objects (keys, thin-head nails, thick-head nails) using feature plots.

### 7. Line Detection with the Hough Transform
- Detect edges in structural images (bridge/poles).
- Compute the Hough transform and interpret peaks (ρ, θ).
- Experiment with thresholds and discuss over/under-detection.

## How to Run

1. Open **`lab1.ipynb`** in Jupyter Notebook or VS Code.
2. Install required dependencies:

   ```bash
   pip install numpy matplotlib opencv-python scikit-image


   ## Download & View Materials

**Jupyter Notebook**  
The full implementation of all Lab 1 experiments is available here:  
[lab1.ipynb](lab1.ipynb)

**Full Lab Report (PDF)**  
Includes figures, explanations, and conclusions:  
[lab1.pdf](lab1.pdf)
