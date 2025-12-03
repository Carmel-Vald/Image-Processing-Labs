Lab 2 – Color Image Processing & RAW Image Reconstruction

This lab focuses on advanced concepts in color image processing using Python.
The experiments include RGB/HSV/L*a*b* color representations, color segmentation, color-channel manipulation, RAW image processing, demosaicing, and white-balance algorithms.

Goals

Understand RGB → HSV → L*a*b* color conversions and the meaning of each channel.

Perform color-based segmentation using thresholds on hue, saturation, and value.

Modify dominant colors in images by manipulating the hue channel.

Analyze the effect of replacing L*, a*, b* channels between images.

Load and process RAW images (Bayer CFA) using demosaicing methods.

Compare demosaicing algorithms: Nearest Neighbor, Bilinear.

Evaluate different white-balance strategies:
Camera WB, Gray World, White Patch.

Compare RAW-processed images to JPEGs produced by the camera.

Repository Contents

lab2.ipynb
Main Python notebook implementing tasks for Lab 2.

lab2.pdf
Full written lab report including figures and explanations.

Main Experiments
1. Color Representation & Segmentation (RGB / HSV)

Display RGB channels separately and observe how each reveals different structures.
Example: red pepper appears bright in R and dark in G and B.

Convert to HSV and inspect:

Hue → base color

Saturation → color intensity

Value → brightness

Generate binary masks based on:

Hue ranges for color selection

High saturation (non-faded colors)

High value (bright regions)

2. Color Replacement via Hue Manipulation

Identify dominant colors using hue thresholds.

Shift hue values cyclically to recolor objects.

Demonstrate visually how recoloring preserves structure while changing appearance.

3. L*a*b* Channel Swapping

Replace L*, a*, b* between two images to observe:

L* controls brightness/contrast → strongest effect on perception.

a* shifts green ↔ red balance.

b* shifts blue ↔ yellow balance.

Show that images retain structure but dramatically change their perceived lighting and color tone depending on the swapped channel.

4. RAW Image Processing & Demosaicing

Work with RAW Bayer-pattern images (14-bit per channel).

Compute pixel count and discuss memory/bit-depth considerations.

Compare JPEG (camera processed) vs RAW (unprocessed):

JPEG: sharpened, gamma-corrected, compressed.

RAW: wider dynamic range, neutral colors, suitable for editing.

5. Demosaicing Algorithms

Nearest Neighbor:

Fast but produces color artifacts (false colors at edges, moiré patterns).

Creates color bleeding in patches of fine textures.

Bilinear Interpolation:

Smoother reconstruction, fewer artifacts.

Still struggles at sharp edges where hue inconsistencies appear.

6. White Balance Algorithms

Camera WB → produces natural colors using camera metadata.

Gray World → assumes global average color is gray.

Works poorly when scene is dominated by green/blue objects.

White Patch → assumes brightest pixel should be white.

Fails in scenes lacking truly white references.

7. Evaluation Across Multiple Images

For three RAW images, compare:

JPEG vs RAW reconstruction

NN vs Bilinear demosaicing

WB methods (Camera, Gray World, White Patch)

Observe:

Contrast/dynamic range differences

Noise and color artifacts

Over- or under-corrections in white balance

Miscolored edges from simple demosaicing

How to Run

Open lab2.ipynb in Jupyter Notebook or VS Code.

Install required packages:

pip install numpy matplotlib opencv-python scikit-image rawpy


Run all cells; figures and comparisons will be generated automatically.

Download & View Materials

Notebook:
lab2.ipynb
