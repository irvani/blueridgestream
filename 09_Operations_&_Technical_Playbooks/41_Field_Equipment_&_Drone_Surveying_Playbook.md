# File 41: Field Equipment, Drone Surveying & Remote Sensing Playbook

> [!NOTE]
> **Field Operations & Remote Sensing Guide**  
> **Target School**: UGAWarnel Forestry / GT CEE Geotechnical & Hydrologic Interns  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Scientific Context: High-End Remote Sensing

To accurately audit our stream reaches and satisfy the **USACE Savannah District 7-year monitoring release schedules**, we cannot rely solely on manual walking tape-measure surveys. 

We utilize advanced **Unmanned Aerial Systems (UAS)** paired with multispectral remote sensing to build precise 3D channel maps and track vegetative growth over time. This playbook details the standard operating procedures for drone surveying, raw orthomosaic processing, and telemetry sensor calibration.

---

## 2. Drone Surveying & Photogrammetry Workflow

We utilize the **DJI Mavic 3 Enterprise (M3E)** drone, equipped with an RTK GPS module for sub-centimeter horizontal and vertical coordinates mapping.

```
                      DRONE photogrammery WORKFLOW
                      
   [ Layout 5 Ground Control Points ] ---> [ Mission Planning: 80/75% Overlap ]
                                                         |
   [ Export GeoTIFF Dem & Ortho ]   <--- [ Process Raw Images in WebODM ]
             |
             v
   [ Generate 3D Point Cloud for AutoCAD & HEC-RAS channel meshes ]
```

### A. Field Ground Control Points (GCP) Layout
Before taking off, you must lay out a minimum of **5 Ground Control Points** across the stream reach to calibrate the photogrammetry model:
1. **Target Design**: Use high-contrast black-and-white $60\text{cm} \times 60\text{cm}$ square checkerboard mats.
2. **Distribution**: Place 4 GCPs at the four corners of the survey reach corridor, and 1 in the middle. Ensure they are placed on flat ground with a clear view of the sky.
3. **RTK GPS Survey**: Use a survey-grade RTK GNSS receiver on a rover pole to capture the exact coordinates (X, Y, Z) of the center of each GCP target, recording them to our coordinate projection system.

### B. Flight Mission Planning
1. **Software**: Use *DJI Pilot 2* to create a grid mapping mission.
2. **Altitude**: Set to exactly **120 feet (36.5 meters)** above the canopy to capture high-density details while ensuring complete obstacle clearance.
3. **Speed**: Set flight speed to **7.5 mph (12 km/h)**.
4. **Camera Parameters**: Trigger the camera based on distance. Enable RTK positioning.
5. **Overlaps**: Set **Front Overlap to 80%** and **Side Overlap to 75%**. High overlaps are non-negotiable to map dense mountain foliage without visual stitching errors.

---

## 3. WebODM Photogrammetry Processing & Point Clouds

Upon completing the flight, transfer the raw geotagged JPEG images to our open-source processing server:

1. **Software**: Open **WebODM (Web OpenDroneMap)** Community Edition on our AWS EC2 instance.
2. **Configuration**: Create a new project. Select the **High Resolution** processing template. Add your 5 RTK-surveyed GCP coordinates to the GCP manager to bind the point cloud to our StatePlane grid.
3. **Processing Output**: Run the orthomosaic process. Extract three primary files:
   - **Orthomosaic (.tif)**: High-resolution ($1.5\text{ cm/pixel}$) visual map.
   - **Digital Elevation Model (DEM .tif)**: High-precision surface map.
   - **Dense Point Cloud (.las)**: Billions of georeferenced points used in AutoCAD Civil 3D to construct stream cross-sections.

---

## 4. Multispectral Vegetation Index (NDVI) Modeling

To satisfy USACE Year 5 vegetative canopy milestones, you will process multispectral imagery in QGIS to calculate the **NDVI (Normalized Difference Vegetation Index)**. This mathematically proves our plantings are expanding and healthy:

$$\text{NDVI} = \frac{\text{NIR} - \text{RED}}{\text{NIR} + \text{RED}}$$

Where:
- $\text{NIR} = \text{Near-Infrared reflection band from our drone sensor}$.
- $\text{RED} = \text{Visible red reflection band}$.

### NDVI Target Indicators:
- **Barren Soil / Eroded Clay**: $\text{NDVI} < 0.1$.
- **Stressed Riparian Vegetation**: $\text{NDVI} = 0.2\text{--}0.4$.
- **Lush, Healthy Native Canopy (Mature Rhododendron)**: $\text{NDVI} \ge 0.65$.

---

## 5. Telemetry Sensor Calibration & Maintenance

You must calibrate our primary water telemetry equipment before every field deployment to prevent data drift:

### A. YSI ProDSS Multiparameter Probe Calibration
- **Dissolved Oxygen (DO)**: Perform a air-saturated calibration. Place the probe inside the damp storage cup (saturated with water), wait 10 minutes for temperature stabilization, and calibrate the DO reading to local barometric pressure ($100\%$ saturation).
- **pH Calibration**: Execute a **three-point calibration** using fresh buffer solutions of pH 4.01, 7.00, and 10.01. Rinse the probe with distilled water between buffer buffing.
- **Conductivity Calibration**: Use a standard $1,000\,\mu\text{S/cm}$ calibration standard.

### B. Field Maintenance Log
Keep a physical logbook in our equipment trailer detailing: *Date, Probe Serial Number, Pre-Calibration Readings, Buffer Batch Numbers, Post-Calibration Verification, and Wader Decontamination Sign-offs*. Any instrument showing a calibration drift $>5\%$ between site deployments must be sent back to our technical office for membrane replacement.
