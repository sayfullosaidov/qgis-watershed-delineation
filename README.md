# Watershed Delineation with QGIS and GRASS GIS

A reproducible GIS workflow for delineating a watershed from a Digital Elevation Model (DEM) using **QGIS** and **GRASS GIS**.

The project demonstrates a basic terrain-to-watershed workflow: preparing a DEM, correcting depressions, deriving drainage networks, identifying an outlet, and delineating the upstream contributing watershed.

## Workflow

The general workflow is:

```text
Digital Elevation Model (DEM)
          ↓
      Fill Sinks
          ↓
  Flow Direction / Accumulation
          ↓
     River Network
          ↓
    Identify Outlet
          ↓
  Watershed Delineation
          ↓
   Watershed Boundary
```

## Tools

* [QGIS](https://qgis.org/)
* GRASS GIS
* Digital Elevation Model (DEM)
* Raster terrain analysis
* Hydrologic network analysis

## Method

### 1. DEM Preparation

A Digital Elevation Model is imported into QGIS and prepared for hydrologic analysis.

The DEM represents the elevation of the terrain and provides the basis for determining how water would theoretically flow across the landscape.

### 2. Fill Depressions / Sinks

Small artificial depressions in the DEM can interrupt continuous drainage paths.

A sink-filling algorithm is therefore applied to create a hydrologically conditioned DEM suitable for flow-routing analysis.

### 3. Derive Flow

Flow direction and/or flow accumulation are calculated from the conditioned DEM.

Flow accumulation helps identify locations where drainage converges and provides a way to extract an approximate river or drainage network.

### 4. Extract the River Network

A flow-accumulation threshold is used to identify cells that represent concentrated drainage.

The resulting network provides a visual representation of the drainage structure and helps identify potential watershed outlets.

### 5. Define the Outlet

An outlet point is selected at the location where the watershed drains into the downstream river or drainage system.

The outlet is an important input because the delineated watershed depends on its location.

### 6. Delineate the Watershed

Using the conditioned DEM and outlet location, the upstream contributing area is delineated.

The final result is a watershed boundary representing the area that theoretically drains to the selected outlet.

## Outputs

The workflow produces:

* Hydrologically conditioned DEM
* Flow accumulation raster
* Derived drainage/river network
* Outlet point
* Delineated watershed boundary

Example output:

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
├── scripts/
│   └── README.md
│
├── README.md
└── LICENSE
```

## Why This Workflow?

Watershed delineation is a fundamental step in hydrology and water-resources engineering.

The same general concept is used as a starting point for applications such as:

* rainfall–runoff modeling
* flood modeling
* streamflow analysis
* water-resources planning
* hydrologic model setup
* catchment characterization

This project was created as a practical exercise in connecting **terrain analysis, GIS, and hydrologic processes**.

## Important Limitations

The delineated watershed is dependent on the quality and resolution of the DEM, the hydrologic conditioning method, the flow-routing algorithm, and the selected outlet location.

The extracted river network should therefore not automatically be interpreted as a representation of the actual mapped river system.

This workflow is primarily a **GIS-based terrain analysis**, rather than a complete hydrologic or hydraulic model. It does not by itself simulate precipitation, infiltration, runoff generation, streamflow, or flood depth.

## Reproducibility

The goal of this repository is to document the workflow clearly enough that another user can reproduce the analysis using the same DEM, software settings, and outlet location.

Software versions, processing parameters, and data sources should be recorded as the project is developed.

## Next Steps

Possible extensions include:

* comparing the extracted drainage network with observed river data
* testing different flow-accumulation thresholds
* comparing different DEM products and resolutions
* calculating watershed area and elevation statistics
* deriving stream-order networks
* adding precipitation and land-cover data
* using the delineated watershed as an input to a rainfall–runoff model

## Author

**Sayfullo Saidov**
Civil and Environmental Engineering, Princeton University

Interested in hydrology, urban water systems, flood modeling, and climate-resilient infrastructure.
