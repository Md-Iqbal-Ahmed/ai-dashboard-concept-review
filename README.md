# AI-Assisted Car Dashboard Concept Review Tool

## Overview
This repository contains a Python-based geometric analysis and pre-validation tool designed to evaluate vehicle interior concepts (Digital Mock-Ups / DMUs) prior to formal CAD review. By automating the extraction of geometric properties and calculating spatial symmetry using KDTree algorithms, this tool helps engineers quickly identify design flaws, surface defects, and asymmetrical deviations in 3D concept models.

## Key Features & Capabilities

* **Dashboard Geometry Analysis:** Automatically calculates fundamental physical properties of the 3D mesh, including vertex/face counts, bounding box dimensions, and surface area.
* **Advanced Symmetry Detection:** Utilizes SciPy's `cKDTree` to perform nearest-neighbor searches between the original and mirrored meshes to compute realistic left-right symmetry deviations. 
* **Surface Quality & Manufacturability Check:** Evaluates the mesh for export readiness by detecting watertightness, Euler characteristics, and degenerate faces.
* **Interactive 3D Visualization:** Generates 3D plots mapping the spatial deviation across the dashboard surface.

## Project Structure

* `/notebook` - Contains the Google Colab / Jupyter notebook with the complete Python pipeline.
* `/reports` - Contains generated analysis reports, screenshots, and 3D visualizations.
* `/test_model` - Contains the sample 3D dashboard mesh used for validation.

---

## Visualizing the Results

### 1. Geometry Analysis & 3D Model Rendering
*Initial extraction of the mesh properties and 3D visualization of the base dashboard model.*

<p align="center">
  <img src="reports/Geomatry report.png" width="600" alt="Dashboard Geometry Model Graph"><br>
  <img src="reports/Dashbord_geomatry model graph.png" width="600" alt="Geometry Report">
</p>

### 2. Symmetry Detection & Spatial Heatmap
*The tool visualizes the model and generates a heatmap showing areas of highest geometric deviation from perfect symmetry, backed by KDTree analysis.*

<p align="center">
  <img src="reports/symetry%20heatmap.png" width="600" alt="Symmetry Heatmap"><br>
  <img src="reports/sysmetry%20analysis.png" width="400" alt="Symmetry Analysis">
  <img src="reports/symetry%20report.png" width="400" alt="Symmetry Report">
</p>

### 3. Surface Quality & Final Concept Review
*Automated engineering reports checking for manufacturing readiness and providing a final weighted concept score.*

<p align="center">
  <img src="reports/surface%20quality%20report.png" width="350" alt="Surface Quality Report"><br>
  <img src="reports/dashboard%20concept%20analysis%20report.png" width="800" alt="Dashboard Concept Analysis Report"><br>
  <img src="reports/final%20report.png" width="800" alt="Final Report">
</p>

---

## How to Run
1. Open the `.ipynb` file located in the `/notebook` folder using Google Colab.
2. Upload a 3D mesh (`.obj` or `.stl`) to your Google Drive or directly into the Colab environment.
3. Update the `MODEL_PATH` variable in the script to point to your uploaded file.
4. Run the cells sequentially to generate the geometry report, symmetry analysis, and surface quality scores.

## Technologies Used
* **Python** 
* **Trimesh** (3D mesh processing and surface analysis)
* **SciPy** (Spatial data structures and KDTree algorithms)
* **NumPy** (Vectorized geometry calculations)
* **Plotly** (Interactive 3D rendering)
