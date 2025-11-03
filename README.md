# 🧪 Lab 1: Image as a 2D Signal (Sampling, Quantization, Histograms, Enhancement)

## 🎯 Objective
To understand how images can be treated as 2D signals by exploring:
- Quantization and bit-depth effects  
- Histogram analysis and contrast stretching  
- Gamma correction (non-linear intensity scaling)  
- Sampling and aliasing behavior

---

## 🖼️ 0) Original Image
**Description:**  
Loaded `peppers.png` (or `cameraman.tif` if unavailable) and converted it to grayscale for processing.

**Figure:**  
`Original_RGB.png`, `Grayscale.png`

---

## 🎚️ 1) Quantization and Bit Depth
**Goal:** Observe how reducing bit depth affects image smoothness.

**Observation:**  
- 8-bit: smooth grayscale transitions.  
- 6-bit: minor banding visible.  
- 4-bit: clear posterization (visible intensity steps).  

**Figure:**  
`Quantization_8bit_6bit_4bit.png`

---

## 📊 2) Histogram and Contrast Stretching
**Goal:** Analyze histogram distribution and apply linear contrast stretching.

**Observation:**  
- Original histogram is concentrated in a narrow midrange.  
- After stretching, histogram spreads across 0–255 → improved visibility of darker and brighter regions.  

**Figure:**  
`Histogram_Original_vs_Stretched.png`  
`Contrast_Stretching.png`

---

## 💡 3) Gamma Correction
**Goal:** Apply non-linear intensity mapping to modify brightness perception.

**Observation:**  
- Gamma < 1 (0.6): brightens midtones.  
- Gamma > 1 (1.6): darkens midtones.  
- Useful for display correction and visual tone adjustments.  

**Figure:**  
`Gamma_Original_vs_06_vs_16.png`

---

## 🧩 4) Sampling and Aliasing
**Goal:** Explore the effect of downsampling and upsampling on image quality.

**Observation:**  
- 10% downsampling removed fine textures.  
- Upscaling (nearest-neighbor) caused blockiness and false patterns (aliasing).  

**Figure:**  
`Sampling_Aliasing.png`

---

## 🧠 5) Reflections

### 1️⃣ Bit-depth vs. Banding
Reducing bit-depth decreases the number of gray levels.  
As bit-depth drops from 8-bit to 4-bit, smooth gradients turn into visible bands (**posterization**).  
This happens because fewer intensity levels cannot represent subtle brightness transitions.

### 2️⃣ Contrast Stretching
Contrast stretching spreads the histogram across the full dynamic range (0–255).  
This improves visibility of mid-tone and shadow details, making the image appear sharper and more balanced in brightness.

### 3️⃣ Downsampling and Aliasing
Aggressive downsampling reduces pixel sampling below the **Nyquist limit**, causing high-frequency details to fold into lower frequencies.  
This results in **aliasing** — seen as jagged edges or unnatural patterns after resizing.

---

## 📦 Files in This Repo
| File | Description |
|------|--------------|
| `lab1_image2D.m` | MATLAB script for all sections |
| `README.md` | Report and reflections |
| `/figures/` | Saved images (montages, histograms, etc.) |

---

## ✅ How to Run
1. Open MATLAB.  
2. Run the script:
   ```matlab
   run('lab1_image2D.m')
