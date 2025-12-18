# Dead Tree Detection Toolbox

`DeadTreeDetection.pyt`

An ArcGIS Pro Python Toolbox for automatically identifying and mapping dead trees within forested areas using high-resolution aerial imagery.

## Toolbox Overview

This custom Python Toolbox (.pyt) provides a streamlined, user-friendly interface within ArcGIS Pro for running a complex geospatial workflow. It encapsulates the entire process from loading imagery to generating final validated dead tree polygons.

## Features

- **Seamless ArcGIS Integration**: Runs as a native tool inside ArcGIS Pro
- **User-Friendly Interface**: Input parameters are set via dialog boxes
- **Parameter Validation**: Built-in checks ensure inputs are valid
- **Progress Reporting**: Provides step-by-step feedback
- **Advanced Processing**: Combines Iso Cluster classification, spectral band thresholding, and morphological operations

## System Requirements

### Essential
- **ArcGIS Pro** (Version 3.0 or higher)
- **Spatial Analyst** extension (Licensed and enabled)
- **Read/Write permissions** to the workspace folder

### Recommended
- Dedicated project geodatabase
- At least 8 GB of RAM (16+ GB for large images)

## Installation

1. **Download the Toolbox**: Obtain the `DeadTreeDetection.pyt` file
2. **Place the Toolbox**: Copy to a permanent location (e.g., `C:\Tools\ArcGIS\Toolboxes`)
3. **Add to ArcGIS Pro**:
   - Open your ArcGIS Pro project
   - In the Catalog pane, right-click on Toolboxes
   - Select Add Toolbox
   - Browse to the .pyt file and click OK

## Tools in the Toolbox

**Primary Tool: Detect Dead Trees**
Runs the complete workflow from input imagery to final dead tree polygons.

## How to Use the Tool

1. **Open the Tool**: Double-click the Detect Dead Trees tool
2. **Set Parameters**:
   - **Input Aerial Imagery**: Select your high-resolution image
   - **Forest Area Mask**: Select polygon feature class or raster mask
   - **Output Workspace**: Select folder or geodatabase for outputs
   - **Output Feature Class Name**: Name for final output
   - **Validation Points** (Optional): Point feature class for accuracy assessment
3. **Run the Tool**: Click the Run button

## Workflow Process

The tool executes these steps automatically:

1. Extract by Mask (clip to forest area)
2. Unsupervised Classification (Iso Cluster)
3. Maximum Likelihood Classification
4. Reclassification (isolate dead tree class)
5. Spectral Filtering (blue band thresholding)
6. Morphological Filtering (clean raster)
7. Vectorization & Generalization
8. Validation (optional spatial join)

## Outputs

- **Final Feature Class**: Polygon feature class of detected dead trees
- **Intermediate Files**: Temporary rasters and feature classes (can be deleted)

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Tool fails to run | Ensure Spatial Analyst extension is enabled |
| Invalid parameter error | Check coordinate systems match |
| No valid output | Check intermediate raster to verify correct class is isolated |
| Tool runs slowly | Use smaller area of interest; avoid network drives |

## License & Disclaimer

**Disclaimer:** This tool is provided "AS IS" for research and educational purposes. Results depend on input imagery quality and spectral characteristics.

**License:** MIT License. Please acknowledge use in published materials.