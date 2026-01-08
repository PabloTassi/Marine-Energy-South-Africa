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

### **Step 1: Clone this repository**
```bash
git clone https://github.com/Pablo.Tassi/Marine-Energy-South-Africa.git
cd Marine-Energy-South-Africa
```

### **Step 2: Install Mamba (recommended) or Conda**

**Option A - Miniforge (includes Mamba)** - Recommended:
1. Download Miniforge from: https://github.com/conda-forge/miniforge
2. Install following the instructions for your operating system
3. Mamba will be available by default

**Option B - Using existing Conda:**
```bash
conda install -n base conda-forge::mamba
```

### **Step 3: Create a dedicated environment**
```bash
mamba create -n marine-energy python=3.11
mamba activate marine-energy
```

### **Step 4: Install the Copernicus Marine Toolbox**
```bash
mamba install -c conda-forge copernicusmarine
```

### **Step 5: Install additional required packages**
```bash
mamba install -c conda-forge numpy pandas xarray matplotlib cartopy cmocean scipy imageio netCDF4
```

Or install everything in one command:
```bash
mamba install -c conda-forge copernicusmarine numpy pandas xarray matplotlib cartopy cmocean scipy imageio netCDF4
```

### **Step 6: Verify installation**
```bash
copernicusmarine --version
```

## 📊 Data Download

### **Prerequisites**
1. **Create a free Copernicus Marine account** at: https://data.marine.copernicus.eu/register
2. **Activate your environment** (if not already active):
   ```bash
   mamba activate marine-energy
   ```

### **Configure your credentials**
Run this command once to save your credentials:
```bash
copernicusmarine login
```
Enter your Copernicus Marine username and password when prompted.

### **Download the required datasets**

The notebook requires oceanographic data for the South Africa region (2025). You can download them using the Copernicus Marine Toolbox:

#### **1. Sea Surface Height (SSH)**
```bash
copernicusmarine subset \
  --dataset-id cmems_obs-sl_glo_phy-ssh_nrt_allsat-l4-duacs-0.25deg_P1D \
  --variable adt \
  --start-datetime 2025-01-01 --end-datetime 2025-12-31 \
  --minimum-longitude 14 --maximum-longitude 34 \
  --minimum-latitude -40 --maximum-latitude -29 \
  --output-directory ./data \
  --output-filename SouthAfrica_SSH_2025.nc
```

#### **2. Ocean Currents**
```bash
copernicusmarine subset \
  --dataset-id cmems_mod_glo_phy_anfc_0.083deg_P1D-m \
  --variable uo --variable vo \
  --start-datetime 2025-01-01 --end-datetime 2025-12-31 \
  --minimum-longitude 14 --maximum-longitude 34 \
  --minimum-latitude -40 --maximum-latitude -29 \
  --output-directory ./data \
  --output-filename SouthAfrica_Currents_2025.nc
```

#### **3. Wave Parameters**
```bash
copernicusmarine subset \
  --dataset-id cmems_mod_glo_wav_anfc_0.083deg_PT3H-i \
  --variable VHM0 --variable VTPK \
  --start-datetime 2025-01-01 --end-datetime 2025-12-31 \
  --minimum-longitude 14 --maximum-longitude 34 \
  --minimum-latitude -40 --maximum-latitude -29 \
  --output-directory ./data \
  --output-filename SouthAfrica_Waves_2025.nc
```

#### **4. Ocean Color (Suspended Particulate Matter)**
```bash
copernicusmarine subset \
  --dataset-id cmems_obs-oc_glo_bgc-plankton_nrt_l4-multi-4km_P1D \
  --variable SPM --variable KD490 --variable ZSD \
  --start-datetime 2025-01-01 --end-datetime 2025-12-31 \
  --minimum-longitude 14 --maximum-longitude 34 \
  --minimum-latitude -40 --maximum-latitude -29 \
  --output-directory ./data \
  --output-filename SouthAfrica_OceanColor_2025.nc
```

### **Alternative: Manual Download**
You can also manually download data from the [Copernicus Marine Data Store](https://data.marine.copernicus.eu):
1. Search for the datasets by their IDs (listed above)
2. Use the web interface to subset and download
3. Place the downloaded `.nc` files in the `data/` folder

**Note:** The dataset IDs provided above are examples. Please verify the exact dataset IDs in the Copernicus Marine catalogue using:
```bash
copernicusmarine describe --include-datasets
```

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
