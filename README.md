# Watershed Delineation with QGIS and GRASS GIS

A GIS-based project demonstrating watershed delineation from a Digital Elevation Model (DEM) using **QGIS** and **GRASS GIS**.

## Workflow

The watershed was delineated through the following steps:

1. **DEM Preparation** – Import and prepare elevation data.
2. **Sink Filling** – Correct depressions to improve drainage continuity.
3. **Flow Analysis** – Calculate flow direction and accumulation.
4. **Drainage Network** – Extract drainage paths using flow accumulation.
5. **Outlet Selection** – Identify the watershed outlet.
6. **Watershed Delineation** – Determine the upstream contributing area.

## Tools

- QGIS
- GRASS GIS
- Digital Elevation Model (DEM)

## Result

The final output is a watershed boundary and derived drainage network based on terrain elevation.

## Limitations

Results depend on DEM resolution, processing methods, and outlet selection. The analysis represents terrain-based drainage patterns rather than a complete hydrologic or hydraulic simulation.

## Author

**Sayfullo Saidov**  
Civil and Environmental Engineering, Princeton University
