<p align="center">
  <img width="128" height="128" alt="ColorInstance" src="https://github.com/user-attachments/assets/8303d5bb-1a62-4072-bac4-92dc5b00fa10" />
</p>

<h1 align="center">ColorInstance</h1>

<p align="center">
  A dedicated, always-accessible macOS floating utility panel designed for UI/UX designers, front-end engineers, technical artists, and shader/game developers who require exact color math, wide-gamut fidelity, and rapid code/asset export.
</p>

---

## Download

Grab the latest **`ColorInstance-1.0.0-arm64.zip`** from the [**Releases**](https://github.com/playbop/ColorInstance/releases) page, unzip it, and drag **ColorInstance.app** into your **Applications** folder.

### Requirements
- **Apple Silicon Mac** (M1 or newer)
- **macOS 14.6 (Sonoma)** or later

### First Launch (Unnotarized Build)
Because this is a free, unnotarized standalone build, macOS Gatekeeper will prompt on the first double-click.

To open it:
1. Try opening **ColorInstance.app** once and dismiss the Gatekeeper prompt.
2. Open **System Settings → Privacy & Security**, scroll down, and click **Open Anyway**.

*(Alternatively, run `xattr -cr /Applications/ColorInstance.app` in Terminal.)*

---

## Screenshots

<p align="center">
  <img width="820" alt="ColorInstance Overview" src="https://github.com/user-attachments/assets/8d331d84-1559-4acd-9172-daa92e46c938" />
</p>

<p align="center">
  <img width="405" alt="ColorInstance Tool View 1" src="https://github.com/user-attachments/assets/3764b089-adb6-4cee-8f58-31536512a12f" />
  &nbsp;
  <img width="405" alt="ColorInstance Tool View 2" src="https://github.com/user-attachments/assets/c467c4b9-a66f-498a-ba88-791322edac7c" />
</p>

<p align="center">
  <img width="405" alt="ColorInstance Tool View 3" src="https://github.com/user-attachments/assets/8667e891-6d36-4be4-b191-eb1bc2d4971b" />
  &nbsp;
  <img width="405" alt="ColorInstance Tool View 4" src="https://github.com/user-attachments/assets/a6a3a1e0-e3dd-4481-b6c8-afd87f8e348c" />
</p>

<p align="center">
  <img width="405" alt="ColorInstance Tool View 5" src="https://github.com/user-attachments/assets/fe3e0a38-3d24-4d6a-939e-268b2ab1ea76" />
  &nbsp;
  <img width="405" alt="ColorInstance Tool View 6" src="https://github.com/user-attachments/assets/0dd265e5-d14b-455c-83ec-ecc5bcdd4f0b" />
</p>

---

## Core Architecture & Color Pipeline

- **Neutral Dark Studio UI:** Built around a calibrated `#0F0F0F` canvas and `#141414` navigation rail to eliminate simultaneous contrast bias when evaluating hues and values.
- **Extended Linear sRGB Reference Model:** Internally stores colors in unclamped extended linear sRGB using a high-precision D65 SIMD matrix pipeline, preserving **Display P3** wide-gamut coordinates alongside **sRGB**, **OKLCH**, **HSL**, **HSB**, and **CIELAB** without destructive round-trip drift.
- **Full Undo/Redo Engine:** Supports discrete command reversal and coalesced high-frequency slider/wheel drag transactions via `⌘Z`, `⇧⌘Z`, and `⌘Y`, while respecting native text undo when editing hex or numeric fields.
- **Persistent Workspace & Quick Recall:** Automatically remembers window screen position (with multi-display bounds validation), active color, working color space, active palette, last-used tool, gradient setup, and custom palettes across launches. If closed with `⌘W`, reopen anytime from the Dock or with `⌘0` (**Window → Show ColorInstance**).

---

## Navigation Rail & Primary Color Inspector

<p align="center">
  <img width="380" alt="ColorInstance Compact Inspector" src="https://github.com/user-attachments/assets/a4731cef-9d10-47dd-9e04-12a358fb4b6c" />
</p>

- **Desktop Eyedropper & HEX Controls:** Sample any pixel on screen, edit or copy `#RRGGBB` hex values with instant visual confirmation, and inspect a `96 pt` live color well.
- **Dynamic Spectrum Channel Sliders:** Four live-gradient sliders (three color channels plus Alpha with checkerboard transparency preview) paired with inline numeric fields that adapt ranges, step increments, and formatting to the active color space.
- **Metal-Accelerated Chromaticity Wheel:** Renders slices of **sRGB**, **Display P3**, **HSL**, **OKLCH**, and **CIELAB** smoothly at 120Hz via Metal (with a CoreGraphics fallback), including:
  - **Gamut Boundary Polygon:** Plots the live in-gamut sRGB boundary in OKLCH and CIELAB slices.
  - **Live Harmony Overlays:** Draws connected chord polygons and secondary nodes for Complementary, Split Complementary, Analogous, Triadic, Accented Analogous, and Tetradic relationships.
  - **Constraint Locks & Snapping:** Toggle **Radial Lock** (lock hue angle, adjust saturation/chroma) or **Circular Lock** (lock saturation/chroma, adjust hue) with optional **Angle Snapping** (`1°`, `5°`, `15°`, `22.5°`, `30°`, `45°`, or `90°`).

---

## Expandable 6-Tool Drawer

### 1. Palette Manager
- **11 Built-in Presets:** Equal-Lightness Rainbow, APCA/WCAG Accessible Pairs, Colorblind-Safe (Okabe-Ito), Apple System Colors, Apple Crayons, Google Material 3 Baseline, Tailwind Neutral Slate, Tailwind Baseline Accents, PICO-8, Solarized Terminal, and Cinematic Teal & Orange.
- **Custom Palettes:** Create, rename, and delete custom swatch collections; append the current hero color or remove individual swatches via right-click.
- **Export Formats:** PNG Swatch Sheet, Adobe Swatch Exchange (`.ase` binary), W3C JSON Design Tokens, CSS `:root` variables, and SwiftUI `[Color]` array snippets.

### 2. Harmonies & Variations
- **Color Value & Tone:** Generates configurable 4–8 step Tints, Shades, and Tones, plus centered Contrast and Saturation scales in OKLCH.
- **Color Chromatic Shifts:** Generates natural shadow-to-highlight Hue-Shifts and Kelvin-inspired Temperature shifts (`10,000K` cool cyan to `2,700K` warm amber).
- **Color Harmonies:** Interactive Monochromatic, Complementary, Split Complementary, Analogous, Triadic, Accented Analogous, and Tetradic swatch strips tailored to the active working color space.

### 3. Gradient Maker
- **Interpolation & Easing:** Supports Stepped (`4–16` clickable bands) and continuous Linear, Ease-In, Ease-Out, and Ease-In-Out curves evaluated in the active color space with achromatic hue preservation.
- **4-Way Directional Compass:** Switch between Top-to-Bottom, Bottom-to-Top, Left-to-Right, and Right-to-Left, with instant start/target hex swapping.
- **Export Formats:** Directional PNG ramp texture (`32×512` / `512×32`, Display P3 tagged when wide gamut), 64-entry 1D DaVinci Resolve `.cube` LUT, Metal/GLSL `float4[]` shader array, CSS `linear-gradient()` (with `color(display-p3 ...)` support), and SwiftUI `LinearGradient` code.

### 4. Isoluminant Hue Spectrum / Equidistant Hue Array
- **Isoluminant Mode (OKLCH & CIELAB):** Generates `6`, `12`, or `24` hues at strictly equal perceptual lightness (`L*`), solving for maximum in-gamut chroma per hue with a live lightness slider (`0–100%`).
- **Equidistant Mode (sRGB, Display P3, HSL, HSB):** Dynamically switches to an equi-angular `4–24` step hue array. Click any band to select the color (preserving slider lightness) or click its hex label to copy.

### 5. WCAG Contrast & Accessibility
- **Live Preview & Ratio:** Tests background and foreground hex pairs against `18 pt` headings, `14 pt` body text, and UI icons with a real-time WCAG 2.1 contrast ratio readout and instant color swap.
- **Threshold Slider & Auto-Fix:** Drag a haptic-snapping contrast slider (magnetic detents at `4.5:1` and `7.0:1`) or click the one-click auto-fix button to solve for a hue-preserving background luminance that meets AA/AAA targets for Large Text, Normal Text, and UI Components.

### 6. Color Vision Deficiency (CVD) Simulator
- **Real-Time LMS Simulation:** Side-by-side split swatches comparing the hero color against Protan (Protanopia/Protanomaly), Deutan (Deuteranopia/Deuteranomaly), Tritan (Tritanopia/Tritanomaly), and Achromat (Achromatopsia/Achromatomaly).
- **Perceptual Delta Metrics:** Reports CIELAB `ΔE` color shift severity (Low, Moderate, High, Monochrome) and `% L*` lightness shift warnings (Major Darkening / Major Lightening) with a built-in metrics guide popover.

---

## License
Free to download and use. Compiled Apple Silicon binary distribution only (source code is not included).
