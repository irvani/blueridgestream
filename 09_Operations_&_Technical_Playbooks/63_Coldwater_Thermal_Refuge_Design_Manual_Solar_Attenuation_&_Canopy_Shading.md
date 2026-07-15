# File 63: Coldwater Thermal Refuge Design Manual: Solar Attenuation & Canopy Shading

> [!IMPORTANT]
> **Fluvial Thermal Design Standard**: This document establishes the thermal restoration standards and canopy design parameters for the Save Our Streams Inc. projects. By applying mathematical Beer-Lambert solar light attenuation models to target specific canopy shading densities and geomorphically sculpting deep, thermally stratified pools that intercept cold groundwater seeps, we secure critical coldwater sanctuaries for wild Brook Trout. This manual details precise physiological thermal limits, canopy solar radiation equations, stratified pool hydraulics, and hyporheic zone design parameters.

---

## I. Wild Trout Thermal Tolerances & Physiological Thresholds

Water temperature is the single most critical environmental factor dictating wild trout survival. Unlike warmwater species, wild Brook Trout (*Salvelinus fontinalis*) and Brown Trout (*Salmo trutta*) are coldwater stenotherms—highly sensitive to thermal stress.

```
                      [WILD TROUT THERMAL RANGE PROFILE (°F)]
                      
   +-------------+-----------------------+-------------------+----------------+
   |   < 45°F    |       45° - 58°       |     58° - 65°     |     > 68°F     |
   +-------------+-----------------------+-------------------+----------------+
   | Dormant:    |  Optimal Spawning     |  Adult Growth     | Critical Stress|
   | Slow Growth |  & Egg Incubation     |  & Active Feeding | & Lethal Range |
   +-------------+-----------------------+-------------------+----------------+
```

### 1. Physiological Stress Indicators:
*   **Optimal Spawning Range (45°F to 55°F / 7.2°C to 12.8°C)**:
    *   Wild Brook trout spawn in autumn as stream temperatures fall into this range. Egg fertilization and early embryonic development require stable, cold temperatures below 52°F to prevent cell mutations.
*   **Adult growth Range (55°F to 65°F / 12.8°C to 18.3°C)**:
    *   Trout feed actively on drifting aquatic macroinvertebrates. Metabolic rates are highly efficient, yielding optimal growth.
*   **Critical Stress Threshold (68°F / 20°C)**:
    *   **"Hoot Owl" Warning**: Water holding capacity for dissolved oxygen drops rapidly. Adult trout exhibit severe respiratory distress, suppress feeding, and experience high lactic acid buildup when hooked by anglers. 
*   **Lethal Threshold (75°F / 23.8°C)**:
    *   Direct physiological failure. Extended exposure (greater than 4 hours) causes proteins to denature, resulting in complete cellular failure and trout mortality.

---

## II. Canopy Shading & Beer-Lambert Solar Attenuation Models

To combat thermal stress on degraded exurban pasture streams, we must prevent direct solar radiation from reaching the water surface. We design our **Riparian Buffer Canopy** using the **Beer-Lambert Light Attenuation Law**:

### 1. The Light Attenuation Model
We calculate the solar radiation reaching the water surface through a dense canopy using this physical equation represented below:

> **I(z) = I_0 * e^(-k * LAI)**

*   *Where*:
    *   **I(z)** is the solar shortwave radiation intensity reaching the water surface in Watts per square meter (W/m^2).
    *   **I_0** is the direct solar radiation intensity above the forest canopy (typically peaking at 800 to 1000 W/m^2 during exurban summer solstices).
    *   **k** is the canopy light-extinction coefficient (a dimensionless constant reflecting leaf orientation, equal to **0.55** for our native deciduously dominated *Rhododendron maximum* buffer).
    *   **LAI** is the Leaf Area Index, defined as the one-sided green leaf area per unit ground surface area (m^2/m^2).

### 2. Design Target: Achieving 96% Solar Shielding
To keep streams cool, we require an attenuation of **96%** of incoming solar energy, meaning:

> **I(z) / I_0 = 0.04  ==>  e^(-0.55 * LAI) = 0.04**

Taking the natural logarithm of both sides:

> **-0.55 * LAI = ln(0.04) = -3.2189  ==>  LAI = -3.2189 / -0.55 = 5.85**

*   **Restoration Standard**: Our Clemson and Georgia Tech forestry interns design planting layouts to target a minimum **LAI of 5.85**. 
*   **Buffer Planting Slices**:
    *   *First Slice (Immediate Bank Edge)*: Mature, wild-transplanted *Rhododendron maximum* (2-meter height minimum) planted at **1.5 meters on-center**.
    *   *Second Slice (Understory)*: *Alnus serrulata* (Tag Alder) and *Cornus amomum* (Silky Dogwood) to bind soils and block lateral morning/evening sunlight.
    *   *Third Slice (Overstory Canopy)*: *Tsuga canadensis* (Eastern Hemlock) and *Acer rubrum* (Red Maple) to provide long-term high-altitude canopy shade.

---

## III. Hydraulics of Deep, Thermally Stratified Pools

Even with dense canopy shading, high air temperatures can raise stream surface temperatures. To counter this, our fluvial engineers design **Deep Stratified Thermal Refuge Pools** using **Rock J-Hooks and Log Cross-Vanes**:

```
                      [CROSS-SECTION OF THERMALLY STRATIFIED REFUGE POOL]
                      
         Upstream Riffle (Velocity ~ 0.5 m/s)
         ~~~~~~~~~~~~~~~~~~~~
                             \  (Plunge Flow)
                              \
                               v  +--------------------------------------------+
                                  | Surface Warm Water Layer (Active Flow)     |
                                  | (Velocity ~ 0.3 m/s, Temp ~ 68°F)          |
                                  +--------------------------------------------+
                                  | Shear Velocity Boundary Layer (Thermocline) |
                                  +--------------------------------------------+
                                  | Cold Water Bottom Pocket (Stratified)     |
                                  | (Velocity < 0.05 m/s, Temp ~ 58°F)        |
                                  +--------------------------------------------+
```

### 1. Plunge Pool Scour Hydraulics
We place **Log Cross-Vanes** perpendicular to the stream flow. The water spilling over the center log drops vertically, creating a localized plunge pool. 
*   *Scour Depth (d_s)*: We calculate plunge-pool depth using the geomorphic scour equation:
    > **d_s = 1.32 * q^(0.54) * H^(0.22) * D50^(-0.11)**
    *   *Where*: **q** is unit discharge (m^3/s per meter width), **H** is the drop height over the log, and **D50** is the median pool substrate diameter.
    *   *Design Target*: We excavate pools to a minimum depth of **1.2m to 1.8m** (4.0 ft to 6.0 ft) to ensure sufficient vertical stratification volume.

### 2. Maintaining Bottom Water Stratification
Under slow-velocity conditions, cold water remains trapped at the bottom of deep pools because cold water is denser than warm water:
*   **The Density Difference**: Water reaches its maximum density at 39.2°F (4.0°C). Warm water at 68°F (20°C) has a density of 998.2 kg/m^3, while cold water at 58°F (14.4°C) has a density of 999.1 kg/m^3.
*   **Shear Velocity Limit (u_star)**: To prevent turbulent mixing from breaking this thermal stratification, bottom shear velocities (**u_star**) must remain below critical values:
    > **u_star = sqrt(g * R * S) < 0.08 m/s**
    *   *Where*: **R** is the pool hydraulic radius, and **S** is the energy slope.
    *   *Bioengineered Protection*: We place large **Root-Wad Structures** and log shelters at the bottom of the pools. This increases hydraulic friction, slowing bottom velocities to near-zero (less than 0.05 m/s) to preserve the cold bottom pocket.

---

## IV. Hyporheic Zone & Groundwater Seepage Dynamics

The ultimate thermal refuge is achieved by geomorphically connecting the stream channel directly to cold groundwater aquifers.

```
                      [HYPORHEIC ZONE GROUNDWATER SEEPAGE INPUT]
                      
                        Upstream Stream Flow (68°F Surface Water)
                        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
                           |
                           v (Downwelling into Gravel Bed)
                        =========================================
                        Gravel Substrate (Hyporheic Active Zone)
                        =========================================
                           ^ (Upwelling Cold Groundwater Seeps 54°F)
                           |
                        Deep Groundwater Aquifer (Constant Annual Temp ~ 54°F)
```

### 1. The Hyporheic Zone Buffer
The **Hyporheic Zone** is the subsurface region beneath and adjacent to the stream bed where surface water and groundwater mix. 
*   *Thermal Buffer Effect*: Water traveling through these gravel beds moves extremely slowly. The gravel acts as a heat exchanger, cooling hot summer water before it upwells back into the stream.
*   *spawning Protection*: We construct sorted gravel bars using clean river gravel (12mm to 25mm). Surface water downwells into the head of these gravel bars, cooling within the hyporheic zone before upwelling directly under spawning trout nests (redds), keeping the eggs cool.

### 2. Intercepting Cold Groundwater Seeps
During our preliminary drone surveys, we utilize **TIR (Thermal Infrared) multispectral drone cameras** to locate cold groundwater seeps emerging along stream banks.
*   *Restoration Design*: We construct our deep stratified pools directly downstream of these coldwater seeps. This intercepts the 54°F (12.2°C) year-round groundwater flows and traps them within our deep, slow-moving pool pockets, creating a highly resilient sanctuary for trout during hot summer months.

---
*Developed by Save Our Streams Inc. Technical Sourcing Operations. Pushed to remote origin under main.*
