# Watershed Delineation with QGIS and GRASS GIS

A GIS workflow for delineating a watershed from a Digital Elevation Model (DEM) using **QGIS** and **GRASS GIS**.

The project demonstrates the basic terrain-to-watershed process: hydrologically conditioning a DEM, deriving drainage patterns, selecting an outlet, and identifying the upstream contributing area.

## Workflow

```text
Digital Elevation Model (DEM)
          ↓
      Fill Sinks
          ↓
Flow Direction / Accumulation
          ↓
   Drainage Network
          ↓
    Select Outlet
          ↓
Watershed Delineation
          ↓
 Watershed Boundary
```

## Tools

- QGIS
- GRASS GIS
- Digital Elevation Model (DEM)
- Raster terrain analysis
- Hydrologic network analysis

## Method

### 1. Prepare the DEM

A DEM is imported into QGIS and used to represent terrain elevation and surface drainage patterns.

### 2. Fill Depressions

Small sinks or artificial depressions are filled to create a hydrologically conditioned DEM and maintain continuous drainage paths.

### 3. Derive Drainage

Flow direction and flow accumulation are calculated from the conditioned DEM. A flow-accumulation threshold is then used to extract an approximate drainage network.

### 4. Select the Outlet

An outlet is identified at the downstream location of interest. Its location determines the upstream area included in the watershed.

### 5. Delineate the Watershed

The upstream contributing area draining to the selected outlet is delineated to produce the final watershed boundary.

## Example Output

![Watershed delineation](figures/watershed_result.png)

## Project Structure

```text
qgis-watershed-delineation/
│
├── data/
│   └── README.md
│
├── figures/
│   └── watershed_result.png
│
├── qgis/
│   └── watershed_delineation.qgz
│
├── README.md
└── LICENSE
```

## Limitations

The resulting watershed depends on the DEM resolution, hydrologic conditioning, flow-routing method, drainage threshold, and selected outlet location.

The extracted drainage network represents terrain-based flow paths and should not automatically be interpreted as the actual mapped river or stormwater network.

This project focuses on **GIS-based watershed delineation** rather than hydrologic or hydraulic simulation. It does not simulate processes such as precipitation, infiltration, runoff, streamflow, or flooding.

## Possible Extensions

- Compare derived drainage paths with mapped streams
- Test different flow-accumulation thresholds
- Compare DEM products and resolutions
- Calculate watershed area and elevation statistics
- Derive stream order
- Add precipitation or land-cover data
- Use the watershed in a rainfall–runoff model

## Author

**Sayfullo Saidov**  
Civil and Environmental Engineering, Princeton University

Interests: hydrology, urban water systems, flood modeling, and climate-resilient infrastructure.
