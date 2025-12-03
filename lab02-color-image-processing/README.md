# Lab 2 – Color Image Processing & RAW Image Reconstruction

This lab introduces advanced tools in color image processing using Python.
The experiments cover color-space conversions (RGB, HSV, L*a*b*), color segmentation,
hue manipulation, channel swapping, RAW (Bayer) image processing, demosaicing,
and white-balance algorithms.

## Goals

- Understand RGB → HSV → L*a*b* color-space conversions and their channel meanings.
- Perform color segmentation using thresholds on hue, saturation, and value.
- Modify object appearance by shifting hue values.
- Replace L*, a*, b* channels between images and observe visual effects.
- Load and process RAW Bayer-pattern images.
- Compare demosaicing algorithms (Nearest Neighbor, Bilinear).
- Apply white-balance methods and evaluate color accuracy.

## Repository Contents

- **`lab2.ipynb`**  
  Main Python notebook implementing all Lab 2 tasks.

- `lab02-name-of-lab/notebooks/`  
  Placeholder folder for optional additional notebooks.

## Main Experiments

### 1. Color-Space Representations
- Display and analyze individual RGB channels.
- Convert images to HSV and examine hue, saturation, and value behavior.
- Use hue thresholds to segment specific colors.

### 2. Hue-Based Color Modification
- Detect dominant object colors.
- Shift hue values to recolor objects while preserving texture.
- Compare natural vs synthetic recolorings.

### 3. L*a*b* Channel Swapping
- Replace L* (brightness), a* (green–red), and b* (blue–yellow) channels between images.
- Observe how each channel influences appearance.
- Discuss which combinations produce natural results.

### 4. RAW Image Processing
- Load images captured in RAW Bayer format.
- Visualize the Bayer pattern (RGGB).
- Compare RAW vs JPEG versions of the same scene.

### 5. Demosaicing Methods
- Implement Nearest-Neighbor demosaicing.
- Implement Bilinear demosaicing.
- Compare color accuracy and edge reconstruction between methods.

### 6. White-Balance Algorithms
- Apply Camera-provided white balance.
- Apply the Gray World assumption method.
- Apply the White Patch method.
- Compare performance on scenes with different illuminations.

## How to Run

1. Open **`lab2.ipynb`** in Jupyter Notebook or VS Code.
2. Install required dependencies:

   ```bash
   pip install numpy matplotlib opencv-python scikit-image rawpy
   ```

   ## Download & View Materials

**Jupyter Notebook**  
The full implementation of all Lab 2 experiments is available here:  
[lab2.ipynb](lab2.ipynb)
