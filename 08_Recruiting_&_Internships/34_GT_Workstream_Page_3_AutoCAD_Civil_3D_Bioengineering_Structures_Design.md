# File 34: GT Intern Workstream — Page 3: AutoCAD Civil 3D Bioengineering Structures Design

> [!NOTE]
> **Hydrologic Engineering & Geomorphic Design Manual**  
> **Target School**: Georgia Institute of Technology (Georgia Tech) School of Civil & Environmental Engineering  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Design Philosophy: Natural channel Re-Meandering

In high-gradient trout streams, standard concrete retaining walls or rock rip-rap dumping are ecologically unacceptable. They destroy aquatic habitat, block macroinvertebrate colonization, and reflect high velocities downstream, causing accelerated erosion elsewhere. 

Instead, you will draft **Natural Channel Design (NCD)** and bioengineered structures using native materials: red cedar logs, oak root-wads, and high-strength geogrid soil lifts. These structures stabilize eroding banks, scour deep cold pools, and mimic historic mountain stream features. Your role as a GT engineering intern is to generate precise, AutoCAD Civil 3D plan-sheets, cross-sections, and detail diagrams.

---

## 2. Technical Drawings & Dimensions for NCD Structures

You will draft four primary bioengineered structures on our site plans:

### A. Rock J-Hook Vane (Flow Deflection & Pool Scour)
- **Description**: A rock structure built along the outer bank of a curve. The "vane" portion slopes upstream, directing fast currents away from the bank, while the downstream "hook" scours a deep central pool.
- **AutoCAD Parameters**:
  - **Vane Angle**: Set between $20\text{ and } 30\text{ degrees}$ relative to the upstream bank tangent.
  - **Slope**: The rock arm must slope down from the bankfull elevation at the bank to the stream bed at $1/3$ the width of the channel.
  - **Hook Rocks**: Position the J-hook rocks in the center of the channel, submerged below the baseflow water surface. Leave gaps of $10\text{--}15\text{ cm}$ between rocks to allow trout passage and scour scour halos.

### B. Double Log Cross-Vane (Grade Control & Pool Scour)
- **Description**: A two-arm log structure crossing the channel, sloping upstream to create a central plunge pool and prevent bed incision (erosion of the stream bed).
- **AutoCAD Parameters**:
  - **Log Material**: Select fresh red cedar or white oak logs ($30\text{--}45\text{ cm}$ diameter).
  - **Throat Width**: The central "weir" gap must span exactly $1/3$ the bankfull width of the channel.
  - **Log Arm Slope**: Slope the log arms upward at $2\text{--}7\%$ from the stream bed to the bankfull bank line.

### C. Cedar Toe-Wood (Bank Stabilization & Woody Habitat)
- **Description**: Layers of overlapping cedar logs and root-wads placed at the toe of a regraded bank curve, covered with soil lifts.
- **AutoCAD Parameters**:
  - **Placement**: Place the cedar logs below the baseflow water line to prevent decay from air exposure.
  - **Root-wad Projection**: Extend the fibrous cedar root-wads outward into the stream channel at a $45\text{-degree}$ angle facing upstream to trap fine gravels and provide cover for large brown trout.

---

## 3. Structural Anchoring & Geotech Calculations

To ensure these cedar structures do not wash away during major floods, you must execute the **Log Gravity Anchoring Calculations**.

```
                       LOG GRAVITY ANCHOR PROFILE
                       
                      BANKFULL WATER STAGE ~~~~~~~~~~~
                                       |
                   [CEDAR LOG]         | Water Depth (H)
                    Volume (V)         |
                                       v
        ============== BEDROCK / CHANNEL BED ==============
                       |               |
         Threaded      |               | Expansion Wedge Bolt
         Epoxy Anchor  |=======#=======| (High-Strength Grout)
                               |
                               | Heavy Steel Cable
                               v
```

The buoyant upward force ($F_b$) acting on a submerged log must be completely countered by the downward gravitational force of the soil/rock overburden and mechanical anchor anchors.

### Anchor Safety Factor Equation:
$$FS_{anchor} = \frac{W_{overburden} + W_{log\_dry}}{F_{buoyant}} \ge 1.5$$

Where:
- $F_{buoyant} = \gamma_{water} \cdot V_{log}$, where $V_{log} = \pi \cdot R^2 \cdot L$ and $\gamma_{water} = 62.4\text{ lb/ft}^3$.
- $W_{log\_dry} = \gamma_{cedar} \cdot V_{log}$, where dry red cedar weight $\gamma_{cedar} \approx 23.0\text{ lb/ft}^3$.
- $W_{overburden} = \text{weight of rocks/soil placed on top of the log keys in the stream bank}$.

### Worked Example:
Calculate the buoyant force and required anchoring weight for a cedar log of radius $R = 0.75\text{ feet}$ and length $L = 12.0\text{ feet}$:

#### 1. Calculate Log Volume ($V_{log}$):
$$V_{log} = \pi \cdot (0.75)^2 \cdot 12 = 21.21\text{ ft}^3$$

#### 2. Calculate Buoyant Force ($F_{buoyant}$):
$$F_{buoyant} = 62.4 \cdot 21.21 = 1,323.5\text{ lbs of upward force}$$

#### 3. Calculate Log Dry Weight ($W_{log\_dry}$):
$$W_{log\_dry} = 23.0 \cdot 21.21 = 487.8\text{ lbs of downward dry weight}$$

#### 4. Calculate Required Overburden/Mechanical Anchor Weight ($W_{req}$) for $FS = 1.5$:
$$1.5 = \frac{W_{req} + 487.8}{1,323.5} \implies W_{req} = (1.5 \cdot 1,323.5) - 487.8 = 1,497.45\text{ lbs}$$

Your design must specify a minimum of **1,500 lbs of mechanical cable-anchors** (epoxied into bedrock or secured using concrete/rock deadman anchors in the bank) to satisfy the $FS_{anchor} \ge 1.5$ safety margin.

---

## 4. Geotechnically-Reinforced Soil Lift (GRSL) Details

To rebuild vertical, stable banks along outer bends, you will detail **Geotechnically-Reinforced Soil Lifts (GRSL)**:
- **Core Fabric**: Specify high-durability, double-walled **coir fiber geotextile wrap (Type 700 or 900)**.
- **Filling**: Pack the inside of the fabric wraps with bank-run compacted gravel ($15\text{-cm}$ base) and rich organic soil ($15\text{-cm}$ top) to promote native root growth.
- **Compaction**: Specify $95\%$ Standard Proctor Density compaction for the soil core.
- **Interlocking**: Wrap the coir fabric around the soil layers in overlapping envelopes, stepping the lifts back at a $1:0.5$ (Horizontal to Vertical) slope. Interleave native willow stakes and tag alder branches between the lifts to bind the system mechanically.
