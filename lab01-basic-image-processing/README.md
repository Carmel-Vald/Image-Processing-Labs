# Lab 1 – Basic Image Processing & Thermal Imaging

This lab introduces fundamental tools in digital image processing using Python.
The experiments are based on visible-light and thermal images and cover dynamic
range, histograms, enhancement, edge detection, morphology, region properties
and Hough-based line detection. :contentReference[oaicite:0]{index=0}

## Goals

- Acquire visible and thermal images with a FLIR XT8-E camera.
- Understand digital image representation, dynamic range and quantization.
- Analyze and manipulate image histograms (contrast, brightness, gamma, equalization).
- Apply spatial filters and edge detectors (Sobel, LoG, Canny).
- Use thresholding and morphological operations to segment objects.
- Extract region properties and use them for basic classification.
- Detect straight lines using the Hough transform.

## Repository Contents

- `notebooks/lab01_image_processing.ipynb`  
  Main Python notebook implementing all tasks.

- `report/lab01_report.pdf`  
  Full lab report with figures, explanations and conclusions.

- `images/` (optional)  
  Selected result figures (histograms, edge maps, segmented images, Hough lines).

## Main Experiments

### 1. Image Acquisition

- Capture three **visible** images and three **thermal** images of the same scene.
- Compare the visual and thermal versions and how intensity encodes temperature. :contentReference[oaicite:1]{index=1}

### 2. Dynamic Range & Histograms

- Inspect min, max and mean pixel values of a grayscale image (e.g. the toucan).
- Plot intensity profiles along selected rows and explain how they relate to the content.
- Add Gaussian noise and analyze how the histogram spreads and how variance changes.
- Compare histograms of a visible image and its thermal counterpart (12-bit vs 8-bit). :contentReference[oaicite:2]{index=2}

### 3. Histogram-Based Enhancement

- Apply **contrast stretching** and **brightness shifting** and view their effect on the histogram.
- Perform **histogram equalization** and observe how the histogram becomes more uniform.
- Use **gamma correction** with different γ values to improve dark / low-contrast images
  (e.g. snow and bubble images) and explain which γ gives the best visual result. :contentReference[oaicite:3]{index=3}

### 4. Edge Detection

- Apply **Sobel**, **Laplacian of Gaussian (LoG)** and **Canny** edge detectors to the
  church image with different thresholds / σ values.
- Select the “best” parameter set by balancing noise suppression and edge preservation.
- Compare performance on visible vs thermal images and explain why thermal edges are
  weaker and coarser. :contentReference[oaicite:4]{index=4}

### 5. Thresholding & Morphology

- Perform global thresholding on object images (tools, rice grains) and examine the
  resulting binary masks.
- Apply **erosion** and **dilation** to remove small details and then recover main objects,
  and discuss what details are lost. :contentReference[oaicite:5]{index=5}
- Use background estimation + subtraction to get a much better separation of rice
  grains from the background, both visually and in the histogram.

### 6. Region Properties & Simple Classification

- Label connected components (keys, nails) and compute region properties
  such as area, convex area, perimeter, eccentricity, solidity, axis lengths.
- Use scatter plots (e.g. *major axis* vs *convex area*, *axis ratio* vs *eccentricity*)
  to cluster objects into: keys, thin-head nails, wide-head nails. :contentReference[oaicite:6]{index=6}

### 7. Line Detection with the Hough Transform

- Detect edges in an image of a bridge / poles and compute the Hough transform.
- Interpret peaks in the Hough parameter space (ρ, θ) as straight lines in the image.
- Experiment with different thresholds and discuss over-detection vs under-detection of
  lines, and possible improvements (e.g. processing image segments). :contentReference[oaicite:7]{index=7}

## How to Run

1. Open `notebooks/lab01_image_processing.ipynb` in Jupyter / VS Code.
2. Make sure the required libraries are installed, e.g.:

   ```bash
   pip install numpy matplotlib opencv-python scikit-image
