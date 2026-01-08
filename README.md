# Marine Energy and Offshore Wind Farm Assessment - South Africa

This Jupyter Notebook provides a comprehensive analysis of oceanographic conditions for offshore wind farm site assessment in South African coastal waters.

## 📚 Course Information
**Institution:** École des Ponts  
**Project:** Marine Energy Assessment 2025  
**Region:** South Africa (40°S to 29°S, 14°E to 34°E)

## 🎯 Learning Objectives

- Analyze oceanographic data from Copernicus Marine Service
- Understand major current systems (Agulhas and Benguela currents)
- Assess sediment transport processes and scour hazards
- Evaluate offshore wind farm site suitability
- Visualize ocean dynamics through animations and plots

## 🔧 Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- Required Python packages (see Installation section)

## 📦 Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/Pablo.Tassi/Marine-Energy-South-Africa.git
   cd Marine-Energy-South-Africa
   ```

2. **Install required packages:**
   ```bash
   pip install numpy pandas xarray matplotlib cartopy cmocean scipy imageio netCDF4
   ```

   Or use the requirements file (if provided):
   ```bash
   pip install -r requirements.txt
   ```

## 📊 Data Download

Students need to download oceanographic data from **Copernicus Marine Service**:

1. **Register** at: https://data.marine.copernicus.eu (free account required)

2. **Download the following datasets** for South Africa region (2025):
   - **Sea Surface Height (SSH)** - Daily
   - **Ocean Currents** - Surface and bottom currents (uo, vo)
   - **Wave Parameters** - Significant wave height, period
   - **Ocean Color** - SPM (Suspended Particulate Matter), KD490, ZSD

3. **Place downloaded `.nc` files** in the `data/` folder

## 🚀 Usage

1. **Open the notebook in VS Code or Jupyter:**
   ```bash
   jupyter notebook JN_MarineEnergy_SouthAfrica.ipynb
   ```
   Or open directly in VS Code with Jupyter extension

2. **Run cells sequentially** - Each section builds on previous analyses

3. **Generated outputs:**
   - Plots saved in `img/` folder
   - Animations saved in `img/animations/` folder

## 📖 Notebook Structure

| Section | Content |
|---------|---------|
| **1. Introduction** | Regional oceanography and current systems |
| **2. Setup** | Python modules and data loading |
| **3. Study Area** | Bathymetry, geography, and domain overview |
| **4. Temporal Variability** | Time series analysis of ocean variables |
| **5. Animations** | Dynamic visualizations (SSH, currents, waves, SPM) |
| **6. Ocean Currents** | Surface and vertical current structure |
| **7. Wave Climate** | Wave statistics and energy potential |
| **8. Sediment Transport** | Shields parameter, bedload transport, scour assessment |
| **9. OWF Assessment** | Offshore wind farm hazard mapping and site selection |
| **10. Exercises** | Student activities and questions |
| **11. Conclusion** | Summary of key findings |
| **12. References** | Scientific literature and data sources |

## 🎨 Key Features

- **Interactive visualizations** using Matplotlib and Cartopy
- **Geospatial analysis** with proper map projections
- **Sediment transport physics** including Shields parameter calculations
- **Hazard assessment** for offshore wind farm installation
- **Animated GIFs** showing temporal evolution of ocean conditions

## 🌊 Main Findings

- **Agulhas Current** (east coast): High-energy zone with scour risks
- **Benguela Current** (west coast): Lower energy, suitable for OWF
- **Recommended OWF site**: Western Cape shelf (18.0-18.6°E, -33.5 to -34.1°N)
  - Low scour risk (bed shear stress < 0.5 Pa)
  - Manageable wave conditions
  - Away from strong current zones

## 📝 License

This material is provided for **educational purposes only**.

## 👥 Authors

Pablo Tassi - Marine Energy Project - Course 2025-2026

## 📧 Contact

For questions or issues, please contact [your email or create GitHub issues]

---

**Note:** This notebook requires access to Copernicus Marine Service data. Students must register and download datasets independently.
