# ΛCDM 2.0 + DUT: Global Cosmology Dashboard

A cutting-edge interactive web-based cosmology simulation and visualization platform designed to explore the **Hubble Tension (H₀)** and **Structure Amplitude (S₈)** problems in modern cosmology using the **Dark Ultra Light Tensor (DUT)** extension to the standard ΛCDM model.

## 🌌 Overview

This dashboard provides real-time visualization and computation of cosmological parameters through an advanced interface combining:

- **3D Matter Field Simulation** using Three.js
- **Interactive Cosmological Charts** powered by Chart.js
- **Mission-based Parameter Exploration** with live metrics
- **Scientifically-grounded Models** including ΛCDM baseline and DUT corrections

The application addresses two critical tensions in modern cosmology:

1. **H₀ Tension**: Discrepancy between early-universe (CMB) and late-universe (SH0ES) Hubble constant measurements
2. **S₈ Tension**: Mismatch between predicted and observed matter clustering amplitude

## 🎯 Key Features

### 1. **3D Visualization Panel**

- Real-time particle field representing cosmic matter structure formation
- **Green particles** = Active growth regions (normal structure formation)
- **Purple particles** = Quenched/suppressed growth (DUT screening effect)
- Interactive 3D rotation and dynamic particle state transitions
- Responsive canvas that adapts to window resizing

### 2. **Cosmological Parameters**

- **H₀ (Hubble Constant)**: Current universe expansion rate [km/s/Mpc]
- **S₈ (Structure Amplitude)**: Matter clustering strength at z=0
- **fσ₈(z) (Growth Rate)**: Linear growth rate of density fluctuations

### 3. **Interactive Controls**

- **Matter Density (Ωm,0)**: Adjust baseline matter density (default: 0.315)
- **DUT Coupling Strength (ξ)**: Control screening effect intensity (default: 0.030)
- **Run Simulation**: Process calibration with 2-second delay animation
- **Export Results**: Copy formatted report to clipboard

### 4. **Evolution Charts**

- **H(z) Evolution**: Hubble parameter as function of redshift
  - Compares ΛCDM 2.0 + DUT vs. ΛCDM baseline
- **fσ₈(z) Growth Rate**: Matter growth rate evolution
  - Shows suppression effect of DUT coupling

### 5. **Mission Timer**

- Real-time elapsed time tracking in HH:MM:SS format
- Simulates ongoing cosmological observation mission

## 📊 Cosmological Data (Fixed Target Values)

The dashboard uses scientifically-grounded target values:

| Parameter              | Value          | Source      |
| ---------------------- | -------------- | ----------- |
| **H₀ (CMB)**           | 67.4 km/s/Mpc  | Planck 2018 |
| **H₀ (Late Universe)** | 73.08 km/s/Mpc | SH0ES 2024  |
| **S₈ (Structure)**     | 0.774          | KiDS/DESI   |
| **fσ₈(0) (Growth)**    | 0.405          | DESI        |

## 🚀 Getting Started

### Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled
- Internet connection (for CDN resources)

### Installation

1. Clone or download this repository
2. Open `index.html` in your web browser
3. The dashboard initializes automatically with default parameters

### Usage

1. **Initial Load**:

   - Dashboard loads cosmological data (simulated 800ms delay)
   - Status indicator transitions from "LOADING ONLINE DATA..." to "READY (DUT Calibrated)"

2. **Adjust Parameters**:

   - Use sliders to modify Ωm,0 and ξ
   - Charts and 3D visualization update in real-time
   - Metrics recalculate instantly

3. **Run Simulation**:

   - Click "🚀 RUN SIMULATION" button
   - Dashboard enters processing state (2-second animation)
   - Metrics finalize with visual pulse effect
   - Status updates to "COMPLETED (DUT Calibrated)"

4. **Export Results**:
   - Click "📋 EXPORT RESULTS" to copy formatted report
   - Report includes all parameters, values, and sources
   - Button confirms with "✅ COPIED!" feedback

## 📐 Technical Implementation

### Architecture

**Frontend Stack**:

- **HTML5**: Semantic markup and responsive layout
- **Tailwind CSS**: Modern utility-first styling with glass-morphism effects
- **Chart.js**: High-performance cosmological curve rendering
- **Three.js**: WebGL-based 3D particle field simulation
- **Vanilla JavaScript**: Core simulation logic and interactivity

### Key Components

#### 1. **Cosmological Models**

```javascript
// ΛCDM H(z) calculation
E(z)² = Ωm,0(1+z)³ + ΩΛ,0
H(z) = H₀ × E(z)
```

#### 2. **DUT Corrections**

- Applies tensor field screening to suppress growth rates
- Boosts H₀ from CMB baseline (67.4) to late-universe value (73.08)
- Suppresses S₈ and fσ₈ via coupling strength parameter ξ

#### 3. **3D Particle System**

- 500 particles simulating matter field
- State transitions: Active (green) ↔ Quenched (purple)
- Transition probability scales with ξ coupling strength
- Smooth rotation and wobble animation

#### 4. **Real-time Updates**

- Slider input events trigger instant chart recalculation
- No data re-fetching required for parameter changes
- Smooth animations with 100ms chart update cycles

### Design Highlights

**Glass-morphism UI**:

- Semi-transparent panels with backdrop blur
- Gradient borders for depth
- Responsive grid layout (mobile-first, scales to desktop)

**Accessibility**:

- High contrast colors for readability
- Clear labeling with scientific notation
- Responsive design adapts to all screen sizes

**Performance**:

- Efficient Three.js particle rendering (500 particles @ 60 FPS)
- Optimized Chart.js with 60-point curves
- Debounced resize listeners
- Minimal re-renders on slider input

## 📋 Data Sources

- **Planck 2018**: Early-universe cosmology from CMB observations
- **SH0ES 2024**: Late-universe H₀ from Cepheid distance ladder
- **KiDS Survey**: Weak lensing cosmic shear measurements
- **DESI**: Dark Energy Spectroscopic Instrument growth rate data

## 🔬 Scientific Context

### The H₀ Tension

The Hubble constant measured from early-universe (CMB) observations (~67.4 km/s/Mpc) significantly differs from late-universe measurements (~73 km/s/Mpc), creating a ~5σ tension that challenges the standard cosmological model.

### The S₈ Tension

Observations of large-scale structure suggest lower matter clustering amplitude than predicted by CMB-based ΛCDM fits, indicating possible modifications to gravitational physics or dark energy properties.

### DUT Solution

The Dark Ultra Light Tensor extension introduces a light scalar degree of freedom that:

- Screens gravitational effects at late times (reconciling H₀)
- Suppresses growth of structure (matching S₈ observations)
- Maintains consistency with CMB constraints

## 🎨 Interface Elements

### Status Indicators

- **Sky Blue (Animated Pulse)**: System ready
- **Amber (Spinning)**: Processing data
- **Green**: Export successful

### Color Scheme

- **Sky Blue (#38bdf8)**: Primary accent, H₀ metric
- **Indigo (#a78bfa)**: S₈ metric
- **Fuchsia (#d946ef)**: fσ₈ metric, DUT curves
- **Slate (#0f172a → #020617)**: Background gradient

### Charts

- **Solid Lines**: ΛCDM 2.0 + DUT model
- **Dashed Lines**: ΛCDM baseline (reference)
- **3D Field**: Green/Purple particle states

## 📱 Responsive Design

- **Mobile** (< 640px): Stacked layout, single-column interface
- **Tablet** (640px - 1024px): 2-column grid for charts
- **Desktop** (> 1024px): Full 5-column layout with 3D + charts side-by-side

## ⚙️ Browser Compatibility

| Browser | Version | Status          |
| ------- | ------- | --------------- |
| Chrome  | 90+     | ✅ Full Support |
| Firefox | 88+     | ✅ Full Support |
| Safari  | 14+     | ✅ Full Support |
| Edge    | 90+     | ✅ Full Support |

## 🔧 Customization

### Modify Base Parameters

Edit these constants in the JavaScript section:

```javascript
const TARGET_COSMO_DATA = {
  H0_CMB: { value: 67.4, source: "Planck 2018" },
  H0_SH0ES: { value: 73.08, source: "SH0ES 2024" },
  S8_LSS: { value: 0.774, source: "KiDS/DESI" },
  FS8_LSS: { value: 0.405, source: "DESI" },
};

const OMEGA_M_BASELINE = 0.315;
const XI_BASELINE = 0.03;
```

### Adjust 3D Simulation

- Modify `particleCount` for particle density
- Change `quenchProb` for faster/slower state transitions
- Adjust `camera.position.z` for zoom level

## 📚 References

- Planck Collaboration (2018): _Planck 2018 results_
- Riess et al. (2024): _A comprehensive measurement of the local value of the Hubble constant with 1 km/s/Mpc uncertainty_
- Amodeo et al. (2021): _Tensions in Cosmology from Early and Late Universe Measurements_

## 🤝 Contributing

This dashboard is part of the ExtractoDAO ΛCDM 2.0 research initiative. Contributions and suggestions are welcome.

## 📄 License

Open-source cosmology research tool. Available under MIT License.

---

**Last Updated**: November 30, 2025
**Version**: 2.0
**Status**: Production Ready
