# ColorInstance

A fast, standalone macOS color inspector and palette studio built natively for **Apple Silicon**.

## Download
Grab the latest **`ColorInstance-1.0.0-arm64.zip`** from the [**Releases**](https://github.com/YOUR-USERNAME/ColorInstance/releases) page, unzip it, and drag **ColorInstance.app** into your **Applications** folder.

### Requirements
- **Apple Silicon Mac** (M1 or newer)
- **macOS 14.0 (Sonoma)** or later

---

## Features
- **Primary Color Inspector:** Desktop eyedropper, HEX input, and real-time conversion across **sRGB**, **Display P3**, **OKLCH**, **HSL**, **HSB**, and **LAB**.
- **Metal-Accelerated Chromaticity Wheel:** Live harmony overlays, radial/circular locks, angle snapping, and sRGB gamut boundaries in OKLCH/LAB.
- **Palette Manager:** 11 built-in presets + editable custom palettes. Export as **PNG**, **Adobe `.ase`**, **JSON tokens**, **CSS variables**, or **SwiftUI `[Color]`**.
- **Harmonies & Variations:** Tints, shades, tones, contrast, saturation, hue-shifts, temperature shifts, and polar harmonies.
- **Gradient Maker:** Stepped, linear, and eased gradients across any working space. Export as **PNG ramp**, **1D `.cube` LUT**, **Metal/GLSL `float4[]`**, **CSS**, or **SwiftUI `LinearGradient`**.
- **Isoluminant Hue Spectrum / Equidistant Array:** Constant-luminance OKLCH/LAB stepped spectrums and equi-angular arrays.
- **WCAG 2.1 Contrast Tool:** Live text/icon preview, magnetic `4.5:1` / `7.0:1` threshold slider, and one-click hue-preserving auto-fix.
- **CVD Simulation:** Protan, Deutan, Tritan, and Achromat simulations with $\Delta E$ and `% L*` shift metrics.

---
Screenshots

<p align="center">
  <img width="256" height="256" alt="ColorInstance" src="https://github.com/user-attachments/assets/8303d5bb-1a62-4072-bac4-92dc5b00fa10" />
</p>
<p align="center">
  <img width="420" height="581" alt="Screenshot 2026-11-24 at 12 13 38" src="https://github.com/user-attachments/assets/a4731cef-9d10-47dd-9e04-12a358fb4b6c" />
</p>
<p align="center">
  <img width="1030" height="566" alt="Screenshot_0" src="https://github.com/user-attachments/assets/8d331d84-1559-4acd-9172-daa92e46c938" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_1" src="https://github.com/user-attachments/assets/3764b089-adb6-4cee-8f58-31536512a12f" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_2" src="https://github.com/user-attachments/assets/c467c4b9-a66f-498a-ba88-791322edac7c" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_3" src="https://github.com/user-attachments/assets/8667e891-6d36-4be4-b191-eb1bc2d4971b" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_4" src="https://github.com/user-attachments/assets/a6a3a1e0-e3dd-4481-b6c8-afd87f8e348c" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_5" src="https://github.com/user-attachments/assets/fe3e0a38-3d24-4d6a-939e-268b2ab1ea76" />
</p>
<p align="center">
  <img width="748" height="584" alt="Screenshot_6" src="https://github.com/user-attachments/assets/0dd265e5-d14b-455c-83ec-ecc5bcdd4f0b" />
</p>

---

## First Launch (Unnotarized Build)
Because this is a free, unnotarized standalone build, macOS Gatekeeper will block the first double-click.

To open it:
1. Try opening **ColorInstance.app** once (dismiss the Gatekeeper prompt).
2. Open **System Settings → Privacy & Security**, scroll down, and click **Open Anyway**.

*(Or via Terminal: `xattr -cr /Applications/ColorInstance.app`)*

---

## License
Free to download and use. Compiled binary distribution only (source code is not included).
