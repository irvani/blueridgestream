# File 32: GT Intern Workstream — Page 1: Rosgen Stream Classification & Field Survey Processing

> [!NOTE]
> **Hydrologic Engineering & Geomorphic Design Manual**  
> **Target School**: Georgia Institute of Technology (Georgia Tech) School of Civil & Environmental Engineering  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Scientific Principles: Natural Channel Design (NCD)

As a Geomorphology & Hydrologic Engineering Intern from Georgia Tech, you are responsible for translating physical stream surveys into stable, self-scouring channel geometries. 

We utilize Dave Rosgen's **Natural Channel Design (NCD)** methodology. Degraded mountain streams are often in a state of high geomorphic instability, characterized by rapid lateral erosion (Type F or G channels) due to historic bank modifications. Our design goal is to transition these unstable reaches back to their stable historic geomorphic types (typically **Rosgen B or C channels** in montane ecoregions). 

Your first task is to process field-collected cross-section, longitudinal profile, and substrate data to calculate the baseline and design geomorphic parameters.

---

## 2. Geomorphic Parameters and Core Equations

You will use the following standard equations to process stream survey spreadsheets:

```
                      STREAM CROSS-SECTION GEOMETRY
                      
                           Floodprone Width (Wfp)
     |<----------------------------------------------------------------->|
     
                         Bankfull Width (Wbkf)
                         |<------------------>|
     
     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~  Floodprone Stage = 2 x Dmax
     --------------------|                  |------  Bankfull Stage (Dmax)
                         |   o   o.  o.  o  |
                         | o.  o.  o.  o.  o|
                         \__________________/
                            Stream Bed Sand/Cobble
```

### A. Entrenchment Ratio ($ER$)
The entrenchment ratio measures the degree of vertical containment of a stream channel within its valley, representing the stream's access to its active floodplain.

$$ER = \frac{W_{fp}}{W_{bkf}}$$

Where:
- $W_{bkf} = \text{Bankfull Width (width of channel at bankfull water stage)}$.
- $W_{fp} = \text{Floodprone Width (width of valley at an elevation equal to twice the maximum bankfull depth, } 2 \cdot D_{max})$.
- *Classification*: Stable Rosgen B and C channels require $ER \ge 1.4$ (moderately to slightly entrenched). An $ER < 1.4$ indicates severe channel incision (incapable of flooding onto the valley flats, resulting in high shear stress and bank collapse).

### B. Width-to-Depth Ratio ($WDR$)
The width-to-depth ratio indicates the channel's cross-sectional shape and is a primary indicator of sediment transport capacity.

$$WDR = \frac{W_{bkf}}{d_{mean}}$$

Where:
- $d_{mean} = \text{Mean bankfull depth } (A_{bkf} / W_{bkf})$, where $A_{bkf}$ is the bankfull cross-sectional area.
- *Classification*: Stable high-gradient mountain streams (B-type) typically maintain a $WDR$ between $12$ and $20$. An overwidened stream ($WDR > 25$) experiences a drop in shear stress, causing heavy silt deposition.

### C. Sinuosity ($K$)
Sinuosity measures the degree of stream meandering.

$$K = \frac{L_{channel}}{L_{valley}}$$

Where:
- $L_{channel} = \text{Stream channel length measured along the thalweg (deepest point of flow)}$.
- $L_{valley} = \text{Straight-line valley length between the upstream and downstream points}$.

---

## 3. Step-by-Step Geomorphic Survey Processing

You will compile field-collected total station or RTK GPS coordinates to classify the stream reach:

### Step 1: Process the Cross-Section Data
1. Open the survey CSV sheet containing *Station (x)* and *Elevation (y)* points across the channel cross-section.
2. Identify the **Bankfull Stage** elevation (marked by geomorphic indicators in the field, such as the top of flat depositional benches or changes in vegetation).
3. Calculate the bankfull area ($A_{bkf}$), bankfull width ($W_{bkf}$), and maximum depth ($D_{max}$) relative to this elevation.
4. Calculate $d_{mean} = A_{bkf} / W_{bkf}$.

### Step 2: Process the Longitudinal Profile Data
1. Extract the elevation points along the channel thalweg, bankfull stage, and water surface over a length of at least 20 stream widths.
2. Calculate the average channel slope ($S$):
   $$S = \frac{\text{Thalweg Elevation}_{up} - \text{Thalweg Elevation}_{down}}{\text{Stream Length}}$$
3. Identify pool-to-pool spacing and riffle slopes.

### Step 3: Classify the Substrate ($D_{50}$)
1. Plot the Wolman Pebble Count data as a cumulative percent finer curve.
2. Extract the **$D_{50}$** value (the particle size at which $50\%$ of the substrate is finer).
3. If $D_{50} = 0.5\text{ mm}$, substrate is sand (Rosgen designation 5). If $D_{50} = 22\text{ mm}$, substrate is gravel (designation 4). If $D_{50} = 90\text{ mm}$, substrate is cobble (designation 3).

---

## 4. Geomorphic Rosgen Classification Lookup Matrix

Using the parameters calculated above, classify your stream reach according to the following lookup matrix:

| Stream Type | Entrenchment Ratio ($ER$) | Width/Depth ($WDR$) | Sinuosity ($K$) | Slope ($S$) | Geomorphic Description |
|:---:|:---:|:---:|:---:|:---:|---|
| **A** | $< 1.4$ (Highly Entrenched) | $< 12$ | $1.0\text{--}1.2$ | $> 0.04$ | Steep, entrenched, cascading step-pool stream. |
| **B** | $1.4\text{--}2.2$ (Moderately Entrenched) | $> 12$ | $> 1.2$ | $0.02\text{--}0.04$ | Stable, rapids and rapids-dominated steps, low erosion risk. |
| **C** | $> 2.2$ (Slightly Entrenched) | $> 12$ | $> 1.2$ | $< 0.02$ | Meandering pool-riffle channel with broad floodplain. |
| **F** | $< 1.4$ (Entrenched) | $> 12$ (Very Wide) | $> 1.2$ | $< 0.02$ | Highly unstable, entrenched, severely widening stream bend. |
| **G** | $< 1.4$ (Entrenched) | $< 12$ (Very Narrow) | $> 1.2$ | $0.02\text{--}0.04$ | Unstable "gully" channel with active severe bank slumping. |

*Restoration Goal*: If a reach is classified as an eroding **F4** channel, your AutoCAD designs must narrower the bankfull channel and create a new floodplain bench to transition it to a stable **C4** or **B4** channel.
