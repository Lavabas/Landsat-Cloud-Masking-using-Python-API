# Cloud-Free NDVI Generation from Landsat Imagery via the Earth Engine Python API 
## Overview

This project demonstrates cloud masking and vegetation monitoring using Landsat 8 and Landsat 9 Surface Reflectance imagery through the Google Earth Engine Python API (via xee and geemap) for a selected region in Trincomalee District, Sri Lanka.
The workflow extracts cloud-free NDVI (Normalized Difference Vegetation Index) maps by identifying and masking clouds, cirrus, and shadows using the QA_PIXEL band. NDVI, derived from near-infrared (NIR) and red bands, is a widely used measure of vegetation greenness and health.
By integrating automated cloud masking and temporal smoothing, this workflow produces cleaner, more consistent vegetation signals across time, ideal for studying seasonal vegetation patterns and long-term environmental dynamics.


### Figure 1. Cloud-masked NDVI composites derived from Landsat 9 imagery (2024–2025) over the Trincomalee region.
<img width="1736" height="1190" alt="image" src="https://github.com/user-attachments/assets/30f52a7a-3da5-4719-8373-8783792b4d7d" />

### Figure 2. Temporally smoothed NDVI series using a 7-image rolling mean over Trincomalee.
<img width="1736" height="1190" alt="image" src="https://github.com/user-attachments/assets/71c60315-1273-4c98-81dd-27bafb3798bf" />

## Datasets

| Dataset                     | Description                                               | Source                    |
| --------------------------- | --------------------------------------------------------- | ------------------------- |
| **LANDSAT/LC08/C02/T1\_L2** | Landsat 8 Collection 2 Level-2 Surface Reflectance        | USGS / NASA               |
| **LANDSAT/LC09/C02/T1\_L2** | Landsat 9 Collection 2 Level-2 Surface Reflectance        | USGS / NASA               |
| **QA\_PIXEL**               | Quality band used for cloud, cirrus, and shadow detection | Included in dataset       |
| **Bands Used**              | SR\_B4 (Red), SR\_B5 (NIR)                                | Used for NDVI computation |


 ## Tools & Libraries
1. Google Earth Engine (GEE) – Satellite data access and processing
2. xee – Bridge between GEE and xarray for local analysis
3. geemap – Interactive map visualization and ROI selection
4. xarray – Handling multi-dimensional climate & remote sensing data
5. matplotlib – Visualization of NDVI maps and time-series

## Notes
- Cloud masking significantly improves vegetation signal quality and reduces outliers.
- The default RdBu colormap emphasizes NDVI contrasts — consider RdYlGn for vegetation-focused outputs.
- This workflow can be extended to drought monitoring, crop health analysis, or land-cover change studies.

## References
1. USGS (2024). Landsat Collection 2 Level-2 Data Products.
2. Tucker, C. J. (1979). Red and photographic infrared linear combinations for monitoring vegetation. Remote Sensing of Environment.
