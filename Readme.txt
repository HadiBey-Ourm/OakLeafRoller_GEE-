# Oak Leaf-Roller Moth Study - Sentinel-2 Pipeline

## Overview
This repository contains Google Earth Engine (GEE) scripts to preprocess Sentinel-2 imagery (2018–2024) for monitoring oak leaf-roller moth (T. viridana) impact on forest canopy in West Azarbaijan, Iran.

## Study Area
- Zagros forests, southern West Azarbaijan (Piranshahr and Sardasht)
- Provided as a FeatureCollection: `projects/ee-hbig6399/assets/Sar`

## Data
- Sentinel-2 Level-2A Surface Reflectance Harmonized
- Cloud masking using S2cloudless probability (<30%) with 200m buffer

## Workflow
1. Filter Sentinel-2 images for the period 21 March – 22 October each year
2. Apply cloud masking
3. Calculate NDVI, EVI, and NDWI
4. Create median composite for visualization
5. Generate decline map based on thresholds (NDVI<0.7, EVI<0.7, NDWI<0.3)
6. Export daily mean indices (CSV) for BFAST time-series analysis

## Exports
- `GEE_Exports/Decline_Map_<year>.tif`
- `GEE_Exports/Daily_Indices_<year>.csv`

## Notes
- BFAST breakpoints are applied outside GEE using the exported CSVs in R or Python.
- Decline map in GEE is for visualization only; the main analysis is based on BFAST-detected breakpoints.

## Author
- Dr. Hadi Beygi Heidarlou