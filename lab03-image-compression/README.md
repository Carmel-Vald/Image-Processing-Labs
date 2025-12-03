# Lab 3 – Image Compression (Entropy Coding, JPEG, YCbCr)

This lab explores several fundamental techniques in image compression, including entropy-based coding, transform coding, chroma subsampling, and JPEG-style quantization.  
All experiments were implemented in Python using NumPy, OpenCV, and Matplotlib.

---

## Goals

- Understand the relationship between image statistics, histograms, entropy, and compressibility.
- Implement Huffman entropy coding and evaluate compression ratio, PSNR, and SSIM.
- Apply JPEG-style grayscale compression using DCT, quantization, and block processing.
- Investigate how Quality Factor (QF) affects visual quality and objective metrics.
- Extend JPEG compression to color images using the YCbCr color space.
- Compare chroma subsampling methods (4:4:4 vs. 4:2:0) and analyze the trade-off between compression and visual fidelity.

---

## Repository Contents

- **lab3.ipynb**  
  Full implementation of all tasks: entropy coding, grayscale JPEG compression, color JPEG compression, and metric evaluation.

- **/images/**  
  Folder containing example test images (owl, room, city, flowers, candy, thermal image, etc.).

---

## Tasks Overview

### **Task 1 – Introduction to Image Statistics**
- Visual inspection of textures, edges, and structure in images.
- Histogram analysis showing how contrast and smoothness relate to entropy.
- Interpretation of entropy values:  
  - Complex images → wide histograms → high entropy → harder to compress.  
  - Smooth images → narrow histograms → lower entropy → easier to compress.

---

### **Task 2 – Entropy Coding (Huffman)**
- Huffman coding is **lossless**, so:
  - `PSNR → ∞`  
  - `SSIM = 1` (perfect reconstruction)  
- Compression ratio depends heavily on image redundancy:
  - Highly structured / repetitive images compress well (e.g., flowers).
  - Noisy or high-detail images compress poorly (e.g., city).

---

### **Task 3 – Grayscale JPEG-Style Compression**
Implemented stages:
1. Divide into 8×8 blocks  
2. Apply DCT  
3. Quantize using QF-dependent table  
4. Reconstruct using inverse DCT  
5. Compute PSNR, SSIM, and Compression Ratio

Key observations:
- **QF = 1** → Almost no visible degradation.  
- **QF = 2–4** → Details begin to disappear, slight blocking in flat regions.  
- **QF = 8** → Strong artifacts and blockiness, especially in smooth images.

Metrics behave as expected:
- Increasing QF → higher compression ratio  
- Increasing QF → lower PSNR & SSIM

---

### **Task 4 – Color Image Compression (YCbCr + DCT)**
Steps performed:
1. Convert RGB → YCbCr  
2. Optional chroma subsampling (4:4:4 or 4:2:0)  
3. Blockwise DCT and quantization  
4. Huffman entropy coding  
5. Reconstruction and metric evaluation  

Key insights:
- Most visual information resides in **Y (luma)**.  
- Human vision is less sensitive to chroma, so subsampling is efficient.  
- **4:2:0** achieves significantly higher compression, with minor color loss.  
- **4:4:4** preserves color quality but compresses less.

Examples:
- Parrot image compresses very well because large regions have uniform texture.
- Candy image compresses poorly due to high-frequency detail and sharp color transitions.

---

## Main Conclusions

- Compression efficiency strongly depends on image content:  
  Smooth images → high compression, Detailed images → low compression.
- Quality Factor controls the trade-off between compactness and visual fidelity.
- YCbCr separation enables aggressive compression with limited visual impact.
- Chroma subsampling (4:2:0) is highly effective for natural images.
- PSNR reflects pixel error but SSIM better matches human perception.

---
