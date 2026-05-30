# File 29: UGA Intern Workstream — Page 2: Water Quality & Thermal Regime Monitoring

> [!NOTE]
> **Ecology & Biological Monitoring Training Manual**  
> **Target School**: University of Georgia (UGA) Odum School of Ecology / Warnell School of Forestry  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Scientific Context: The Coldwater Thermal Limit

Wild Brook Trout (*Salvelinus fontinalis*) and Brown Trout (*Salmo trutta*) are stenothermic organisms, meaning they can only survive in a very narrow range of cold water temperatures. 

As a stream becomes overwidened due to bank collapse, it slows down and loses its shade canopy, exposing the water column to direct solar radiation. High water temperatures lead to two critical biological failures:
1. **Dissolved Oxygen Depletion**: As water warms, its physical capacity to hold oxygen drops precipitously, suffocating fish.
2. **Metabolic Exhaustion**: A trout's metabolic rate spikes at warm temperatures, demanding more food than a degraded stream can provide.

Your job as a UGA Ecology Intern is to manage the thermal monitoring logging system and calculate the canopy heat-attenuation metrics to satisfy USACE monitoring requirements.

---

## 2. Continuous HOBO Temperature Logger Deployment

To capture the true thermal regimes of our reaches, you will deploy **Onset HOBO Water Temp Pro v2** continuous loggers.

```
                  STREAM PROFILE WITH HOBO LOGGER ANCHOR
                  
       Water Surface ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
                                  |
                                  | Aircraft-Grade SS Cable
                                  |
         [ HOBO LOGGER ] --------[+] PVC Protective Sleeve
         (Suspended in Flow)      |
                                  |
       Stream Bed o.o.o.o.o.o.o.o[X] Expansive Wedge Bolt / Rebar
```

### A. Deployment Protocol
1. **Positioning**: Locate a deep, shaded pool tailout within the main stream channel flow. Avoid placing loggers in stagnant eddies or directly on the stream bed sand (where geothermal ground heat or silt burial can distort readings).
2. **Protection**: Encase the HOBO logger in a heavy-duty PVC protective sleeve drilled with numerous $1.27\text{-cm}$ holes to allow free, continuous water flow while protecting the sensor from debris impacts.
3. **Anchoring**: Secure the protective sleeve to a $1.27\text{-cm}$ epoxy-anchored rebar driven deep into the stream bed or tether it to a bedrock boulder using aircraft-grade stainless steel cables and wedge expansion bolts.
4. **Frequency**: Configure the HOBO logger software to record the stream temperature at exactly **15-minute intervals** continuously from May 1 to September 30 (the critical warm-water window).
5. **Data Retrieval**: Every 30 days, retrieve the logger, connect it to the optical USB base station in the field, download the telemetry log, and check the battery status before redeploying.

---

## 3. Dissolved Oxygen (DO) and Water Quality Appraisals

Alongside continuous thermal logging, you will perform bi-weekly manual water quality assays using a calibrated **YSI ProDSS Multiparameter Meter**.

- **Dissolved Oxygen (DO)**: Brook trout spawning requires a DO concentration $\ge 7.0\text{ mg/L}$. A concentration $<5.0\text{ mg/L}$ causes immediate respiratory failure.
- **pH**: Maintain pH between $6.0$ and $8.5$. High-gradient Blue Ridge streams are susceptible to acid precipitation; log any drop below $5.5$.
- **Conductivity**: Background conductivity in pristine mountain streams is low ($10\text{--}50\,\mu\text{S/cm}$). A sudden spike indicates upstream sediment washouts or agricultural runoff.
- **Turbidity**: Measured in Nephelometric Turbidity Units (NTU). Our trout restoration design target is a baseflow turbidity $<5\text{ NTU}$, protecting spawning gravels from silt-choking.

---

## 4. Canopy Solar Shading & Thermal Attenuation Models

To mathematically prove the cooling benefits of our riparian restorations (specifically the dense planting of native *Rhododendron maximum* canopy buffers), you will calculate the **Solar Radiation Shading Attenuation**.

The amount of solar radiation reaching the stream surface ($I_{stream}$) is modeled by the Beer-Lambert law modified for leaf canopy coverage:

$$I_{stream} = I_{open} \cdot e^{-k \cdot \text{LAI}}$$

Where:
- $I_{open} = \text{incident solar radiation in an unshaded open reach } (\text{typically } 950\text{ W/m}^2 \text{ at summer solstice})$.
- $\text{LAI} = \text{Leaf Area Index of our riparian canopy buffer (dimensionless ratio of leaf area to ground area)}$.
- $k = \text{canopy light extinction coefficient } (\text{for native Rhododendron canopy, } k \approx 0.65)$.

### Worked Example:
If our degraded reach has an $\text{LAI} = 0.2$ (barren pastures), and our restored mature Rhododendron buffer reach has an $\text{LAI} = 5.2$ (lush canopy):

#### 1. Unshaded Reach Solar Load:
$$I_{stream\_unshaded} = 950 \cdot e^{-0.65 \cdot 0.2} = 950 \cdot 0.878 = 834.1\text{ W/m}^2$$

#### 2. Restored Rhododendron Shaded Reach Solar Load:
$$I_{stream\_shaded} = 950 \cdot e^{-0.65 \cdot 5.2} = 950 \cdot 0.034 = 32.3\text{ W/m}^2$$

#### 3. Shading Efficiency:
$$\text{Heat Reduction} = \frac{834.1 - 32.3}{834.1} \times 100\% = 96.1\%$$

By achieving a **$96\%$ reduction in solar thermal loading**, our bioengineered buffer acts as an ecological heat shield, keeping the water column cold and protecting the sensitive spawning thermal limit of native trout!
