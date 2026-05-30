# File 33: GT Intern Workstream — Page 2: 1D & 2D HEC-RAS Hydraulic Modeling

> [!NOTE]
> **Hydrologic Engineering & Geomorphic Design Manual**  
> **Target School**: Georgia Institute of Technology (Georgia Tech) School of Civil & Environmental Engineering  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Engineering Objective: Hydrologic Integrity

When we modify stream geometries and install instream structures (like rock J-hooks or cedar log vanes), we change the local hydraulics. 

Under federal **FEMA** and **USACE Savannah District** rules, we must prove that our instream geomorphic modifications do not restrict floodway capacity or cause a local increase in flood elevations during major storms. You will utilize the USACE **HEC-RAS (Hydraulic Engineering Center's River Analysis System)** software to build 1D and 2D steady-flow models comparing pre-construction (existing) and post-construction (design) conditions. Your modeling must verify a **"No-Rise" ($0.00\text{-foot}$ change)** in flood elevations.

---

## 2. HEC-RAS Model Architecture & Step-by-Step Setup

```
                         HEC-RAS MODEL SIMULATION LOOP
                         
   [ LiDAR DEM Terrain ] ---> [ Setup Geometry Mesh ] ---> [ Establish Cross-Sections ]
                                                                     |
   [ Run 100-Yr Simulation ] <-- [ Define Boundary Q ] <-- [ Select Manning's n ]
             |
             v
   [ No-Rise Audit: Post-Restoration WSEL <= Pre-Restoration WSEL (Error <= 0.00 ft) ]
```

### Step 1: Import Digital Elevation Models (DEM)
1. Download high-resolution USGS **$1\text{-meter}$ bare-earth LiDAR DEMs** corresponding to our watershed.
2. In **RAS Mapper**, set the coordinate projection system (typically NAD 1983 StatePlane Georgia West/East in US Survey Feet). Create a new RAS Terrain using the LiDAR geotiff files.

### Step 2: Establish River Geometry
1. Draw the river centerline along the main channel thalweg flow.
2. Draw bank lines representing the left and right bankfull channel limits.
3. Draw flowpath lines tracking the left and right overbank corridors (where flood flows pass during major storms).
4. Lay out cross-section lines perpendicular to flow, spaced every $30\text{ feet}$ along the reach. Ensure cross-sections extend fully across the entire $100\text{-year}$ floodprone valley width.

### Step 3: Select Manning's Roughness Coefficients ($n$)
Assign roughness coefficients across the cross-sections based on bed material and vegetative density:

- **Main Channel (Restored gravel-cobble bed)**: $n = 0.035\text{--}0.040$.
- **Restored Soil Lifts (dense native grass/sedges)**: $n = 0.045\text{--}0.055$.
- **Riparian Overbanks (dense mature Rhododendron / forest)**: $n = 0.080\text{--}0.120$.

---

## 3. Hydrologic Flow Boundary Conditions ($Q$)

You will run a steady-flow simulation modeling three critical storm events. Calculate your peak discharges ($Q$) utilizing the **USGS StreamStats regression equations** for rural Georgia basins:

$$Q_{100} = a \cdot A^b \cdot P^c$$

Where $A$ is the drainage basin area (sq. miles) and $P$ is the mean annual precipitation (inches).

Input the following boundary conditions:
- **Upstream Boundary**: Input the calculated peak flows ($Q_{2}$, $Q_{10}$, and $Q_{100}$).
- **Downstream Boundary**: Set to **Normal Depth**, utilizing the average thalweg friction slope ($S_f$) calculated from your longitudinal profile survey.

---

## 4. Shear Stress Equations & Spawning Bed Flashing

To ensure our instream geomorphic structures scour pools effectively without causing total gravel washout, you must monitor the **Boundary Shear Stress ($\tau$)** output in HEC-RAS:

$$\tau = \gamma \cdot R_h \cdot S_f$$

Where:
- $\gamma = \text{unit weight of water } (62.4\text{ lb/ft}^3 \text{ or } 9,810\text{ N/m}^3)$.
- $R_h = \text{hydraulic radius } (A/P_w, \text{ where } P_w \text{ is the wetted perimeter})$.
- $S_f = \text{friction slope of the channel reach}$.

### Spawning Gravel Shield Critical Thresholds:
We must calibrate channel widths so that normal bankfull shear stress ($\tau_{bkf}$) exceeds the critical shear stress ($\tau_c$) needed to flush out fine silts ($<2\text{ mm}$), but remains below the critical shear stress needed to mobilize spawning-sized gravels ($15\text{--}40\text{ mm}$):

1. **Silt Mobilization Threshold (flushing fine sands)**:
   $$\tau_{c\_silt} \ge 1.46\text{ N/m}^2$$
2. **Spawning Gravel Stability Threshold (keeping gravels intact)**:
   $$\tau_{c\_gravel} \le 21.85\text{ N/m}^2$$

Verify that HEC-RAS cross-sectional shear stress falls within this stable bed-flashing window ($1.46\text{ N/m}^2 < \tau < 21.85\text{ N/m}^2$) to ensure the stream self-cleans its silt without destroying trout spawning beds.

---

## 5. "No-Rise" Compliance Audit Report

Upon completing the HEC-RAS simulations, execute the following audit step:
1. Export the **Water Surface Elevation (WSEL)** table for the $100\text{-year}$ storm event.
2. Subtract the pre-restoration WSEL from the post-restoration design WSEL at every cross-section:
   $$\Delta \text{WSEL} = \text{WSEL}_{post} - \text{WSEL}_{pre}$$
3. Verify that $\Delta \text{WSEL} \le 0.00\text{ feet}$ across all stations. If any station shows $\Delta \text{WSEL} \ge 0.01\text{ feet}$, you must return to the design geometry, slightly widen the bankfull floodplain bench, and re-run the HEC-RAS model until complete compliance is achieved.
