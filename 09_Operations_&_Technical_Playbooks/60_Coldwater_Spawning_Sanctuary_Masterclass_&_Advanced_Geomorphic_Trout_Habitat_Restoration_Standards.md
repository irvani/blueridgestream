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
*   Pools are excavated immediately downstream of geomechanical rock J-hook vanes to provide deep, thermal refuges (minimum depth **1.2m to 1.8m**) with slow resting currents ($<0.1\text{ m/s}$).

---

## III. Switched-Power Hardware Schematics & Component Interface Wiring

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

## IV. Trout Telemetry REST & GraphQL Integration APIs

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
