# File 60: The Coldwater Spawning Sanctuary Masterclass & Advanced Geomorphic Trout Habitat Restoration Standards

> [!IMPORTANT]
> **Trout Ecology and Engineering Standard**: This document establishes the scientific, geomorphic, and electrical engineering standards for achieving the highest ecological level of coldwater stream restoration. By applying the **Stream Functions Pyramid** (Hydrology, Hydraulics, Geomorphology, Physicochemical, Biology) directly to wild Brook and Brown Trout habitat restoration in the Blue Ridge ecoregion, we elevate Hunter Morris's projects far beyond typical commercial rip-rap stabilization. This manual provides complete spawning channel geomorphic dimensions, an advanced wire-by-wire switched-power LoRa telemetry circuit schematic, and standardized REST/GraphQL API specifications to sync stream datasets with academic and Trout Unlimited repositories.

---

## I. The Stream Functions Pyramid for Trout Restoration

To ensure our restoration projects satisfy the highest standards of conservation science, we evaluate and design all fluvial channels using the **Stream Functions Pyramid** (Harman et al., 2012). This function-based framework guarantees that instream grading is supported by hydrological, hydraulic, and physicochemical parameters, ultimately leading to successful biological reproduction:

```
                  [THE STREAM FUNCTIONS PYRAMID FOR WILD TROUT]
                  
                             /=======================\
                            /    Level 5: BIOLOGY     \  <-- Redds (spawning), macroinvertebrate
                           / (Brook & Brown Spawning)  \     biomass, EPT colonization rates.
                          /=============================\
                         /   Level 4: PHYSICOCHEMICAL    \  <-- Stream Temp < 65°F, Dissolved Oxygen
                        / (Thermal Shading & DO Regimes)  \    > 7.0 mg/L in gravel pore spaces.
                       /===================================\
                      /      Level 3: GEOMORPHOLOGY         \  <-- Pool-riffle sequencing, bankfull stable
                     /  (Rosgen Classification & Gravels)    \     3:1 regrading, Rhododendron maximum geogrid.
                    /=========================================\
                   /           Level 2: HYDRAULICS             \  <-- Flow velocity 0.15–0.45 m/s, pool shear
                  /     (1D/2D HEC-RAS Shear Stress Models)     \     stresses, flood-plain floodplain connectivity.
                 /===============================================\
                /              Level 1: HYDROLOGY                 \  <-- LoRa mesh stage logging, watershed drainage,
               /       (Rainfall-Runoff & Baseflow Logging)        \     HUC-8 basin geomorphic discharge curves.
              /=====================================================\
```

### The Five Functional Levels Applied:

1.  **Level 1: Hydrology (Watershed Flow Dynamics)**
    *   *Metric*: Continuous stage logging via hydrostatic transmitters feeding base gateways.
    *   *Trout Context*: Establishes baseline baseflow discharge curves, ensuring headwater streams maintain dry-season flow volumes required for egg survival in spawning redds.
2.  **Level 2: Hydraulics (Local Fluid Mechanics)**
    *   *Metric*: Bankfull shear stress ($\tau$), flow velocity ($v$), and floodplain connectivity.
    *   *Trout Context*: Riffle flow velocities must remain in the $0.15\text{ m/s} - 0.45\text{ m/s}$ sweep range. High-gradient pool velocities are regulated to provide resting micro-habitats, keeping shear stress below gravel movement thresholds ($1.46\text{ N/m}^2 < \tau < 21.85\text{ N/m}^2$) to prevent redd washout.
3.  **Level 3: Geomorphology (Physical Channel Form)**
    *   *Metric*: Rosgen Classification (Type A-B channels), pebble-count distribution ($D_{50}$ median grain size), and lateral bank stability.
    *   *Trout Context*: Regrading vertical failing banks to stable 3:1 slopes, reinforced with geomechanical *Rhododendron maximum* root-wads. Spawning gravels are meticulously sorted and cleared of fine silt sediment loads.
4.  **Level 4: Physicochemical (Water Quality & Chemistry)**
    *   *Metric*: Continuous water temperature loggers, optical dissolved oxygen (DO), and NTU turbidity.
    *   *Trout Context*: Maintains summer thermal water regimes below $65^\circ\text{F}$ ($18.3^\circ\text{C}$) via dense canopy cover, keeping dissolved oxygen levels above $7.0\text{ mg/L}$ directly in the spawning gravel substrate.
5.  **Level 5: Biology (Ecology & Reproduction)**
    *   *Metric*: Redds count, EPT macroinvertebrate colonization indices (Mayfly, Stonefly, Caddisfly), and trout biomass.
    *   *Trout Context*: The ultimate metric of success. Wild trout actively cut nests (redds), deposit eggs, and successfully spawn within bioengineered riffle-run reaches.

---

## II. Spawning Sanctuary Design Standards

To build the highest-tier spawning sanctuaries, Hunter Morris's restoration crew utilizes these precise geomorphic and ecological design standards:

### 1. Spawning Riffle Geomorphic Parameters
*   **Media Gravel Sorting**: Spawning gravels must be native, washed, and sorted to match species-specific spawning parameters:
    *   *Brook Trout*: $D_{50}$ median grain size of **12mm to 25mm** (coarse pea gravels to small pebbles).
    *   *Brown Trout*: $D_{50}$ median grain size of **15mm to 40mm** (medium pebbles).
*   **Substrate Depth**: Gravel beds must have an active depth of **10cm to 30cm** over a firm, stable base.
*   **Flow Hydraulics (Redd Velocity)**:
    *   *Water Depth*: Riffle spawning zones are designed with depths of **10cm to 45cm** under normal base flows.
    *   *Velocity*: Stream velocities directly above the gravel bed must remain between **0.15 m/s and 0.45 m/s**.
*   **Subsurface Interstitial Flow**: Spawning beds are built immediately upstream of riffle crests (where downwelling occurs), pushing oxygen-rich water ($>7.0\text{ mg/L}$ DO) through the gravel pore spaces to nourish incubating eggs.

### 2. Thermal Shading and Canopy Density Design
Direct solar radiation raises stream temperatures, driving wild trout out of shallow creeks. To ensure stream temperatures remain cool, we design a multi-tiered **Riparian Shade Canopy** using the **Solar Shading Shading Equation**:

$$S_{\text{attenuation}} = 1 - e^{-k \cdot \text{LAI}}$$

*   *Where*: $k$ is the canopy extinction coefficient (typically **0.55** for broadleaf/Rhododendron maximum canopy), and $\text{LAI}$ is the Leaf Area Index.
*   *Design Target*: To achieve a **96% solar radiation reduction** ($S_{\text{attenuation}} = 0.96$), we plant a dense broadleaf canopy targeting a minimum **LAI of 5.8**.
*   *Planting Matrix*: We transplant mature, field-sourced *Rhododendron maximum* and *Alnus serrulata* (Tag Alder) at a spacing density of **1.5 meters on-center** directly along the stream bank edge.

### 3. Pool-to-Riffle Sequencing Ratios
*   High-gradient Blue Ridge stream reaches (Rosgen B3-B4 types) require a pool-to-riffle spacing ratio of **5 to 7 bankfull widths**.
*   Pools are excavated immediately downstream of geomechanical rock J-hook vanes to provide deep, thermal refuges (minimum depth **1.2m to 1.8m**) with slow resting currents (<0.1 m/s).

---

## III. The 'Wonder-Pool' Cascade System (The Geomorphic 'Wonder Bra' Alignment)

For our highest-tier, high-velocity stream restoration projects, we utilize a specialized design standard called the **'Wonder-Pool' Cascade System**. Taking inspiration from architectural and support engineering, this system acts as a "geomorphic lift and support framework" (colloquially termed the *Wonder Bra stream alignment*) that structuralizes degraded, sagging banks and lifts hyporheic stream levels to create a highly oxygenated, thermally stable habitat sequence optimal for wild Brown Trout (`Salmo trutta`).

```
                    THE 'WONDER-POOL' CASCADE SCHEMATIC
                    
     Upstream Riffle          Contour Under-Vane Sill         Plunge Pool Chamber
   [Sorted Spawning Gravel]     (Interlocking Rock Vane)      (Scoured Coldwater Refuge)
     D50: 15mm - 40mm             Lifts Baseflow Water         Depth: 1.5m - 2.5m
   ======================\               /=====\              \
                          \             /       \              \
                           \___________/         \              \___________________
                            Hyporheic Flow        \              Deep Rest Currents
                            (Downwelling DO)       \===> Plunge   (Groundwater Springs)
                                                      Aeration
```

### 1. Fluvial Lift & Structural Support Geomorphology
In degraded agricultural valleys, streams tend to "sag" and widen (Rosgen F or G types), losing pool depth and collapsing laterally. The 'Wonder-Pool' Cascade System restores structure and lift through three unified design elements:
*   **Contour Under-Vanes ("Underwire Sills")**: Constructed using large, heavy interlocking limestone or granite boulders (500 kg to 1,500 kg) placed in an upstream-pointing arch (20 to 30 degrees relative to stream banks) with a 4% to 8% throat slope. These structures act as "underwire support sills," lifting upstream baseflow water levels by 0.3m to 0.6m. This backwater "cushion" reduces erosive bank shear stress, sub-irrigates adjacent wetlands, and forces groundwater recharge.
*   **Fluvial Support Cups (Bioengineered Toe-Wood & Root-Wads)**: We construct interlocking root-wad complexes from field-sourced oak and hemlock trees along the outer bank bends of the pools. By wrapping the root-wads with coconut coir geotextiles and backfilling with gravel, we create structural "cups" that support the vertical banks, preventing bank collapse and providing overhead thermal cover for adult brown trout.
*   **Cascade step-downs ("Step-Ponds")**: The stream is aligned into a series of 3 to 5 successive step-down plunge pools connected by steep, rock-armored chutes. Sinuosity is carefully balanced at K = 1.25 to 1.35.

### 2. High-Oxygen Plunge Pool Aeration Physics
Brown trout require exceptionally high dissolved oxygen levels, particularly in high-temperature seasons or near downstream industrial thermal discharges. Atmospheric gas transfer is programmatically maximized as water plunges over each rock weir sill. 

#### The Game-Gameson Aeration Equation
The oxygen transfer and regeneration across our geomorphic weir steps are modeled by the **Game-Gameson Equation**:

r = 1 + 0.38 · a · b · H · (1 - 0.11 · H) · (1 + 0.046 · T)

*   *Where*:
    *   **r** is the oxygen deficit ratio, defined as (Cs - Cin) / (Cs - Cout).
    *   **Cs** is the temperature-dependent saturation concentration of dissolved oxygen (mg/L).
    *   **Cin** is the dissolved oxygen concentration of the water entering the cascade step (mg/L).
    *   **Cout** is the regenerated dissolved oxygen concentration of the water exiting the cascade step (mg/L).
    *   **a** is the water quality parameter (we use a strict conservative standard of 1.25 for clean, high-clarity mountain trout streams).
    *   **b** is the structure geometry parameter (1.00 for simple flat step-weirs; we design curved rock J-hooks that induce intense focal turbulence and vortex mixing, achieving b = 1.35).
    *   **H** is the hydraulic drop height per step (meters, design target H = 0.45m to 0.60m).
    *   **T** is the water temperature (°C).

*   *Fluvial Design Impact*: If an upstream degraded stretch suffers from low-flow hypoxia (Cin = 5.2 mg/L at a summer temperature of 18.0°C, where Cs = 9.45 mg/L), passing through a 3-step 'Wonder-Pool' Cascade (total drop H_total = 1.5m over curved sills b = 1.35) regenerates the deficit ratio (r ≈ 2.12), elevating downstream dissolved oxygen to a highly oxygenated Cout = 8.65 mg/L.

### 3. Substrate Self-Scouring Bed Mechanics
The tail-out of each plunge pool serves as the spawning sanctuary bed. To ensure that fine silts (<2mm) do not settle and cement these spawning gravels, the bed shear stress (τ) must be concentrated to scour sediment without washing away the medium-sized pebbles (D50 = 15mm to 40mm) required for brown trout spawning redds.

#### The DuBoys Shear Stress Model
The active boundary shear stress in the plunge pool throat is calculated using the **DuBoys Equation**:

τ = γ · R · S

*   *Where*:
    *   **τ** is the boundary shear stress (N/m²).
    *   **γ** is the unit weight of water (9,810 N/m³).
    *   **R** is the hydraulic radius (meters, design R = 0.65m in the pool throat during bankfull flows).
    *   **S** is the local energy slope (0.008 during 2-year bankfull events).

*   *Sediment Flushing Design*: This geomorphic design yields an active pool throat shear stress of τ ≈ 51.0 N/m² during bankfull events. According to Shields' critical shear stress threshold curve, fine sand and agricultural silts are scoured and suspended at a critical stress of τ_c = 0.25 to 1.8 N/m², whereas spawning pebbles (D50 = 22mm) remain structurally stable, requiring a shear stress exceeding τ_c = 15.6 N/m² to mobilize. This discrepancy guarantees that fine silts are aggressively flushed out of the plunge pool chambers, depositing sorted, silt-free spawning gravels at the tail-outs.

---

## IV. Switched-Power Hardware Schematics & Component Interface Wiring

To ensure long-term, off-grid telemetry operation on a small **3.7V 3200mAh LiFePO4 battery**, we cannot leave our high-draw 12V Modbus sensors powered continuously. We utilize a **Switched-Power MOSFET Rail** controlled by a microcontroller GPIO pin to apply 12V boost power only during measurement windows.

### 1. Complete wire-by-wire Schematic
This ASCII circuit diagram shows exactly how to connect the WisBlock/ESP32, MAX485 transceiver, MT3608 boost regulator, and AO3401 P-Channel MOSFET switch:

```
                                [STREAM NODE SWITCHED-POWER SCHEMATIC]

  3.7V battery (LiFePO4)
      +     -
     [+]---[-]--------------------------------------------------------------------------+
      |     |                                                                           |
      |     v (GND)                                                                     v
      |   +---------------------------------------+                               +-----------+
      +-->| IN+    [MT3608 12V Boost Regulator]   |                               |  MAX485   |
          | IN-                                   |                               |           |
          | OUT+ (Boosted 12V Rail)   OUT- (GND)  |                               |  VCC (3.3)|<--+ 3.3V (WisBlock)
          +--|--------------------------|---------+                               |  GND      |<--+ GND (WisBlock)
             |                          |                                         |  RO (RX)  |--> WisBlock GPIO 16
             v                          v (GND)                                   |  DI (TX)  |<-- WisBlock GPIO 17
      +------------+                    |                                         |  DE / RE  |<-- WisBlock GPIO 4 (Shorted)
      | [AO3401]   |                    |                                         |  A (+)    |--+ RS485 Differential A+
      | P-MOSFET   |                    |                                         |  B (-)    |--+ RS485 Differential B-
      | Source     |                    |                                         +-----------+
      | Drain      |--+ 12V Switched    |
      | Gate       |  |   VCC to Sensors|
      +----|-------+  |                 |
           |          v                 v
           |     +----------+      +----------+
           |     | DS-DO    |      | TJ-F04   |  (12V Modbus Sensors)
           |     | Optical  |      | Pressure |
           |     | DO       |      | Level    |
           |     +----------+      +----------+
           |
           +---------------------+
                                 |
                                 v
                              [2N2222 NPN BJT Pre-Driver]
                              Collector
                              Emitter   ======> GND
                              Base      <====== WisBlock GPIO 12 (via 1k Ohm Resistor)
```

### 2. Component Pin-to-Pin Connection Schedule
Use this exact wiring layout to assemble the streamside PCB node:

| Source Component | Pin Name | Target Component | Pin Name | Connection Wire Purpose |
| :--- | :--- | :--- | :--- | :--- |
| **WisBlock / ESP32** | **3.3V OUT** | **MAX485 Chip** | **VCC** | Provides 3.3V logic power to transceiver. |
| **WisBlock / ESP32** | **GND** | **MAX485 Chip** | **GND** | Common ground line. |
| **WisBlock / ESP32** | **GPIO 16** | **MAX485 Chip** | **RO (Receive Out)** | Telemetry Serial RX line. |
| **WisBlock / ESP32** | **GPIO 17** | **MAX485 Chip** | **DI (Driver In)** | Telemetry Serial TX line. |
| **WisBlock / ESP32** | **GPIO 4** | **MAX485 Chip** | **DE & RE (Shorted)** | half-duplex Transmit/Receive enable pin. |
| **WisBlock / ESP32** | **GPIO 12** | **2N2222 BJT** | **Base (via 1k resistor)**| Power switch trigger pin. |
| **MT3608 Boost** | **OUT+ (12V)** | **AO3401 P-MOS** | **Source** | Boosted 12V power supply feed. |
| **AO3401 P-MOS** | **Gate** | **2N2222 BJT** | **Collector** | Pulled LOW to activate P-MOS power rail. |
| **AO3401 P-MOS** | **Drain** | **All Sensors** | **VCC (Industrial 12V)**| Switched 12V power output to sensors. |
| **2N2222 BJT** | **Emitter** | **System GND** | **GND** | Ground for BJT switch. |
| **MAX485 Chip** | **A (+)** | **All Sensors** | **Yellow/Green (A+)** | RS485 Differential A+ line. |
| **MAX485 Chip** | **B (-)** | **All Sensors** | **Blue/White (B-)** | RS485 Differential B- line. |

---

## V. Trout Telemetry REST & GraphQL Integration APIs

Our streamside base gateway operates a private REST API database replication layer that synchronizes environmental data with national conservation repositories.

### 1. Unified Biological Correlation REST Ingress
Endpoint: `POST https://science.tu.org/api/v1/ingress/blue_ridge/biological-sync`

This API payload maps real-time water quality parameters directly against monthly macroeconomic macroinvertebrate colonization counts, validating geomorphic restabilization in real time:

```json
{
  "ingress_token": "brsr_science_token_secure_2026",
  "metadata": {
    "station_id": "BRSR-LO-101",
    "station_moniker": "Upper Toccoa headwater Spawning Sanctuary 2",
    "huc_8_watershed": "06020003",
    "stream_name": "Anderson Creek",
    "county": "Fannin County",
    "state": "GA"
  },
  "water_quality_averages": {
    "sampling_window_start": "2026-05-01T00:00:00Z",
    "sampling_window_end": "2026-05-31T00:00:00Z",
    "mean_temperature_f": 57.42,
    "max_temperature_f": 62.15,
    "mean_dissolved_oxygen_mg_l": 9.45,
    "mean_turbidity_ntu": 12.8,
    "sediment_status": "EXCELLENT_GRAVEL_CLARITY"
  },
  "biological_field_metrics": {
    "benthic_sample_date": "2026-05-28T14:30:00Z",
    "macroinvertebrate_ept_index": 22,
    "stoneflies_count_pct": 28.5,
    "mayflies_count_pct": 35.0,
    "caddisflies_count_pct": 20.5,
    "taxa_richness": 18,
    "redd_nest_count": 8,
    "brook_trout_spawning_verified": true
  },
  "geomorphic_validation": {
    "bankfull_width_m": 4.12,
    "mean_bank_stability_rating": "STABLE_BIOENGINEERED_RHODODENDRON",
    "riffle_shear_stress_n_m2": 14.85,
    "pebble_count_d50_mm": 18.2
  }
}
```

### 2. UGA Warnell GraphQL Telemetry Sourcing API
Warnell researchers pull localized ecoregion data using a high-performance **GraphQL API** to build climate water thermal warning models. 

#### Warnell GraphQL Query Structure:
```graphql
query GetTroutThermalRegime($stationId: String!, $huc8: String!, $startDate: DateTime!) {
  streamMonitoringStation(stationId: $stationId, huc8: $huc8) {
    stationName
    elevationMeters
    geomorphicReachType
    hourlyLogs(from: $startDate) {
      timestamp
      waterQuality {
        temperatureC
        dissolvedOxygenMgL
        oxygenSaturationPct
        turbidityNtu
      }
      hydrology {
        stageLevelMeters
        dischargeCfs
      }
      hootOwlAlertActive
    }
  }
}
```

#### Warnell GraphQL JSON Response:
```json
{
  "data": {
    "streamMonitoringStation": {
      "stationName": "Anderson Creek Bio-Reserve 2",
      "elevationMeters": 680.5,
      "geomorphicReachType": "Rosgen B3 Spawning Riffle",
      "hourlyLogs": [
        {
          "timestamp": "2026-05-30T18:00:00Z",
          "waterQuality": {
            "temperatureC": 14.85,
            "dissolvedOxygenMgL": 9.42,
            "oxygenSaturationPct": 91.2,
            "turbidityNtu": 10.5
          },
          "hydrology": {
            "stageLevelMeters": 0.412,
            "dischargeCfs": 18.5
          },
          "hootOwlAlertActive": false
        }
      ]
    }
  }
}
```

---
*Developed by Blue Ridge Stream Restoration Technical Sourcing Operations. Pushed to remote origin under main.*
