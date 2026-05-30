# File 61: Off-Grid Telemetry Node PCBA Manufacturing & Chinese Factory Sourcing Manual

> [!IMPORTANT]
> **Industrial PCBA and Assembly Standard**: This document establishes the master manufacturing blueprint and factory sourcing manual for the Blue Ridge Stream Restoration telemetry nodes. By outsourcing PCB fabrication, component placement (PCBA), and final enclosure assembly directly to rapid-turnover factories in China (such as JLCPCB or PCBWay), we achieve high-quality hardware builds at a fraction of standard commercial costs. This manual provides specific Gerber file requirements, an exact LCSC-coded production Bill of Materials (BOM), physical waterproof NEMA enclosure layouts, and firmware provisioning configurations to compile and launch our Meshtastic stream telemetry nodes.

---

## I. Chinese PCB/PCBA Sourcing & RFQ Pipeline

To procure robust streamside telemetry nodes, Hunter Morris and his operations team bypass local electronics brokers and source directly from vetted, high-precision prototyping houses in Shenzhen (JLCPCB or PCBWay). 

### 1. Vetted Manufacturing Partners
*   **JLCPCB (Shenzhen Jielichuang Electronic Co., Ltd.)**
    *   *Best For*: Fast-turnaround PCB prototyping, low-cost SMT component assembly (PCBA), and turnkey LCSC part catalog integration.
    *   *Web Portal*: `jlcpcb.com`
*   **PCBWay (Shenzhen PCBWay Technology Co., Ltd.)**
    *   *Best For*: Premium multi-layer stackups, advanced impedance matching, customized box-build assembly, and robust QA inspection cycles.
    *   *Web Portal*: `pcbway.com`

### 2. Request for Quote (RFQ) Pipeline
When uploading hardware designs to the factory portal, Hunter's interns submit the following standard **RFQ Sourcing Package**:

```
                              [FACTORY SOURCING PACKAGE]
                              
           1. GERBER FILES (.zip)   ===> Contains copper tracks, soldermask, silkscreen, drill pits.
           2. BOM SPREADSHEET (.xlsx) ===> Catalogs LCSC part numbers, descriptions, quantities.
           3. CPL / Centroid (.csv) ===> Dictates X-Y placement coordinates and rotation vectors.
```

---

## II. Gerber Manufacturing & Multi-Layer Stackup Settings

To guarantee reliable high-frequency RF transmission (915 MHz LoRa band) and stable low-power switching, our stream node is designed on a **4-layer printed circuit board (PCB)**. 

### 1. 4-Layer Controlled Impedance Stackup
Hunter's hardware designers specify this exact layer stackup inside the factory online portal to ensure low noise and 50-Ohm antenna track impedance matching:

```
                      [4-LAYER PCB STACKUP PROFILE]
                      
   Layer 1: TOP COPPER (Signal / RF Tracks)  <=== 0.035mm (1 oz Copper)
   ----------------------------- Prepreg (Isola 370HR or equal) --- 0.2mm thick
   Layer 2: INNER GROUND PLANE (Solid GND)   <=== 0.017mm (0.5 oz Copper)
   ----------------------------- Core (FR4 High-TG150) ------------ 1.0mm thick
   Layer 3: INNER POWER PLANE (3.3V Switched)<=== 0.017mm (0.5 oz Copper)
   ----------------------------- Prepreg (Isola 370HR) ------------ 0.2mm thick
   Layer 4: BOTTOM COPPER (Low-Frequency Sign)<=== 0.035mm (1 oz Copper)
   
   Total PCB Nominal Thickness: 1.6mm
```

### 2. Required Gerber Specification settings:
*   **Material Type**: FR4 Standard (High-TG150 rating to withstand exurban summer stream humidity and sub-zero winter temperatures).
*   **Layer Count**: 4 Layers.
*   **Board Thickness**: 1.6mm.
*   **Finished Copper Weight**: 1 oz Outer Layers, 0.5 oz Inner Layers.
*   **Solder Mask Color**: Matte Green or Matte Black (high contrast for optical inspection).
*   **Silkscreen Color**: Bright White.
*   **Surface Finish**: Lead-Free HASL (Hot Air Solder Leveling) or ENIG (Electroless Nickel Immersion Gold) for enhanced corrosion protection in damp river gorges.
*   **Controlled Impedance**: **Yes (50 Ohm)**. The RF trace connecting the RAK4631 antenna pad to the IPEX connector must be calculated using coplanar waveguide formulas matching the prepreg thickness.

---

## III. Production Bill of Materials (BOM)

To utilize automated SMT placement services, we must source components matching the factory's LCSC database. Hunter’s operations crew uses this exact production **BOM Schedule**:

| Component ID | Footprint Reference | Quantity | Part Description & Value | Vetted Manufacturer | LCSC Part Number | Sourcing Role |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **U1** | WisBlock Core | 1 | RAK4631 nRF52840 BLE LoRa | RAKwireless | **C512398** | Central low-power processing MCU. |
| **U2** | SOIC-8-150mil | 1 | MAX485ESA TTL-to-RS485 Transceiver | Analog Devices / Maxim | **C17485** | Serial differential Modbus driver. |
| **U3** | SOT-23 | 1 | AO3401 P-Channel MOSFET (-30V, -4A) | Alpha & Omega Semi | **C14856** | 12V Switched power gate switch. |
| **Q1** | SOT-23 | 1 | 2N2222 NPN Transistor (40V, 800mA) | Jiangsu Changjing | **C2867** | Pre-driver gate signal level converter. |
| **U4** | SOT-23-6 | 1 | MT3608 1.2MHz Step-Up Boost Regulator | Aerosemi | **C84852** | Boosts battery 3.7V to 12V DC for sensors. |
| **U5** | SOP-8-PP | 1 | TP4056 Linear LiFePO4 battery Charger | TopPower | **C98453** | Manages solar-panel charging rail. |
| **D1-D2** | SOD-123 | 2 | 1N5819 Schottky Diode (40V, 1A) | ON Semiconductor | **C18549** | Reverse-voltage circuit protection. |
| **R1, R2** | 0805 | 2 | 10k Ohm Thick Film Resistor (1%) | Yageo | **C25813** | Gate pull-up & circuit load resistors. |
| **R3** | 0805 | 1 | 1k Ohm Thick Film Resistor (1%) | Yageo | **C25810** | BJT Base limit resistor. |
| **C1, C2** | 1206 | 2 | 10uF Ceramic Capacitor (25V, X7R) | Samsung Electro | **C18520** | Boost converter bypass smoothing caps. |
| **CON1** | IPEX-1 (U.FL) | 1 | IPEX Coaxial Surface Mount Connector | Hirose | **C41852** | Secure antenna RF cable terminal. |
| **J1-J4** | JST-PH-2.0 | 4 | JST PH 2-Pin Right-Angle Headers | JST | **C18523** | Battery, Solar, and sensor connections. |

---

## IV. Enclosure Box & Physical Gland Assembly Layout

Streamside environmental sensors are exposed to high humidity, flood splattering, and animal tampering. Hunter Morris's operations interns assemble each node into a ruggedized, waterproof **Field Enclosure Box** using these strict assembly layout guidelines:

```
                            [FIELD WATERPROOF ENCLOSURE BOX LAYOUT]
                            
           +--------------------------------------------------------------+
           | [6V 5W Monocrystalline Solar Panel Bracket Mount]           |
           |                                                              |
           |    +----------------------------------------------------+    |
           |    | NEMA-67 ABS Waterproof Enclosure Box               |    |
           |    |                                                    |    |
           |    |   +------------------+     +------------------+    |    |
           |    |   | 3.7V 3200mAh     |     | WisBlock PCBA    |    |    |
           |    |   | LiFePO4 Battery  |     | telemetry Core   |    |    |
           |    |   |                  |     |                  |    |    |
           |    |   +--------|---------+     +--------|---------+    |    |
           |    |            |                        |              |    |
           |    +------------|------------------------|--------------+    |
           +-----------------|------------------------|-------------------+
                             |                        |
                             v                        v
                        [PG9 Gland 1]            [PG9 Gland 2]
                        (Solar +12V Feed)        (RS485 Modbus Cable to Creek)
```

### Physical Assembly Guidelines:
1.  **NEMA-67 ABS Enclosure**: We utilize a heavy-duty **ABS NEMA-67 waterproof box** (internal dimensions approximately $150\text{mm} \times 100\text{mm} \times 70\text{mm}$) fitted with a silicone rubber gasket and stainless steel lid screws.
2.  **Cable Ingress PG9 Glands**: Drill two holes in the bottom wall of the enclosure. Install two brass **PG9 waterproof compression glands** (supporting cable diameters $4\text{mm} - 8\text{mm}$).
    *   *Gland 1*: Feeds the switched 12V 4-wire shielded sensor cable directly into the stream channel.
    *   *Gland 2*: Connects the 2-pin monocrystalline solar panel charging lead.
3.  **Waterproofing Drip Loops**: The cables must run downwards out of the glands and loop upwards before running to the stream or solar panel, preventing rain droplets from running along the wire directly into the gland face.
4.  **Barometric Compensation Vent**: For hydrostatic stage level level gauges (such as Model TJ-F04-Modbus) that require a vented capillary tube open to the atmosphere, install a waterproof, breathable **Gore-Tex Pressure Relief Vent** in the bottom wall of the box. This prevents moisture ingress while equalizing internal barometric pressure shifts.
5.  **Secure Battery Bracket**: Secure the 3.7V LiFePO4 battery inside the enclosure using a custom-printed PETG bracket and marine-grade double-sided adhesive, preventing movement during field deployments.

---

## V. Firmware Provisioning & 256-Bit Encryption Key Setup

Once the PCBA is received from Shenzhen and placed in the box, Hunter’s recruitment interns flash the latest **Meshtastic Serial API firmware** to establish communication over our decentralized 915 MHz LoRa mesh network:

### 1. Command-Line (CLI) Firmware Flash SOP
Run these terminal commands on your field laptop to flash the node microcontroller using the **esptool** (for ESP32 nodes) or **uf2-conv** (for RAK4631 nRF52 nodes):

```bash
# 1. Update the Meshtastic Command-Line Python tool
pip install --upgrade meshtastic

# 2. Flash the latest firmware binary over USB Serial
meshtastic --flash-device firmware-rak4631-915mhz-2.4.15.bin

# 3. Provision the device station moniker
meshtastic --set-owner "BRSR-LO-101" --set-owner-short "LO1"
```

### 2. Switched-Power Modbus Query C++ Firmware Code
Upload this C++ block to the WisBlock node using the Arduino IDE to control the switched-power rail and serialize Modbus sensor sweeps:

```cpp
#include <Arduino.h>

#define SWITCH_POWER_PIN 12  // Control Pin for Switched 12V MOSFET
#define DE_RE_PIN 4          // MAX485 Transceiver Transmit/Receive Enable Pin

// Modbus Query Frame: Read Holding Register 0x0001 (optical dissolved oxygen) from Slave ID 0x01
const byte doQueryFrame[] = {0x01, 0x03, 0x00, 0x01, 0x00, 0x01, 0xD5, 0xCA};
byte sensorBuffer[9];

void setup() {
  pinMode(SWITCH_POWER_PIN, OUTPUT);
  pinMode(DE_RE_PIN, OUTPUT);
  
  digitalWrite(SWITCH_POWER_PIN, HIGH); // Cut sensor 12V power supply (MOSFET Switch OFF)
  digitalWrite(DE_RE_PIN, LOW);         // MAX485 in Receive Mode
  
  Serial.begin(115200);
  Serial1.begin(9600, SERIAL_8N1);      // Switched RS485 Serial connection to sensors
}

void loop() {
  // 1. Wake Up Switched-Power Rail
  digitalWrite(SWITCH_POWER_PIN, LOW);  // Pull Gate LOW via NPN pre-driver, turning 12V Rail ON
  delay(5000);                          // Wait 5 seconds for Optical DO and Level sensor warm-up
  
  // 2. Clear Serial buffer
  while(Serial1.available() > 0) { Serial1.read(); }
  
  // 3. Set MAX485 to TRANSMIT (TX) Mode
  digitalWrite(DE_RE_PIN, HIGH);
  delay(10);
  
  // 4. Send Modbus Query
  Serial1.write(doQueryFrame, sizeof(doQueryFrame));
  Serial1.flush();
  
  // 5. Instantly switch MAX485 back to RECEIVE (RX) Mode
  digitalWrite(DE_RE_PIN, LOW);
  
  // 6. Read sensor response with a 500ms timeout
  unsigned long startWait = millis();
  int byteIndex = 0;
  while ((millis() - startWait < 500) && (byteIndex < 7)) {
    if (Serial1.available() > 0) {
      sensorBuffer[byteIndex] = Serial1.read();
      byteIndex++;
    }
  }
  
  // 7. Cut sensor power to preserve battery
  digitalWrite(SWITCH_POWER_PIN, HIGH); // Cut 12V Rail (MOSFET Switch OFF)
  
  if (byteIndex >= 7) {
    // Extract raw register bytes and parse DO mg/L
    unsigned int rawDOVal = (sensorBuffer[3] << 8) | sensorBuffer[4];
    float dissolvedOxygenMgL = rawDOVal / 100.0;
    
    Serial.print("SUCCESS: Checked streamside Dissolved Oxygen = ");
    Serial.print(dissolvedOxygenMgL);
    Serial.println(" mg/L");
  } else {
    Serial.println("ERROR: Modbus connection timed out. Telemetry check failed.");
  }
  
  // 8. Sleep for 15 minutes before the next geomorphic telemetry sweep
  delay(900000);
}
```

### 3. Mesh Network Security: 256-Bit AES Encryption Channel Configuration
To protect landowners from data mining or unauthorized stream tracking, the telemetry data is encrypted using a unique, 256-bit AES private key. Run these CLI commands on the gateway and sensor nodes to establish our secure channel:

```bash
# 1. Create a secure, private 256-bit AES channel called "TroutScience"
meshtastic --create-channel "TroutScience"

# 2. Set the channel encryption key (UETA-compliant private secure key)
meshtastic --set-chan-key "brsr_science_telemetry_aes_256_secure_key_2026_morris" --chan-index 1

# 3. Disable anonymous public mapping beacons to protect stream locations
meshtastic --set position_broadcast_secs 0
```

---

## VI. Base Station Gateway Computer Enclosure & Industrial Box-Build Sourcing

For the central data collection hub located at Co-Founder Hunter Morris's base cabin or mounted on high tower masts, a standard plastic case is insufficient. The base station gateway computer—typically a high-performance **Raspberry Pi 5** or **Radxa Rock 5**—must be housed in a rugged, EMI-shielded, and thermally optimized industrial **Extruded Aluminum Box-Build Enclosure**. This setup processes real-time geomorphic stream data and handles timeseries databases (SQLite/InfluxDB) without thermal throttling or SD card corruption.

### 1. Industrial Extruded Aluminum Enclosure Dimensions & Mechanical Sourcing
*   **Supplier**: **Shenzhen Szomk Electronic Co., Ltd. (SZOMK)** or **Foshan Nanhai Yonggu Technology Co., Ltd. (Yonggu)**
*   **Model/Part Number**: **SZOMK AK-C-B80** or **Yonggu standard extruded aluminum chassis (120mm x 97mm x 40mm)**
*   **Material**: Extruded Aluminum Alloy 6063-T5 with Anodized Finish (Silver/Matte Black) for superior thermal conductivity and corrosion resistance.
*   **Mounting**: Integrated flanged mounting tabs for secure screw-down panel or wall installations. Optional DIN-rail clips.

### 2. Internal Components & Hardware Stackup Layout
The gateway computer uses an industrial stackup that eliminates mechanical weaknesses (such as fragile micro-SD cards) and supports multi-channel LoRa concentrators:

```
                  [BASE STATION GATEWAY COMPUTER INTERNAL STACKUP]

         +--------------------------------------------------------------+
         | Industrial Anodized Aluminum Extruded Chassis (AK-C-B80)     |
         |                                                              |
         |  +--------------------------------------------------------+  |
         |  | RAK5146 LoRaWAN / Meshtastic Concentrator Pi HAT       |  |
         |  +---------------------------|----------------------------+  |
         |                              | 40-Pin GPIO Header            |
         |  +---------------------------v----------------------------+  |
         |  | Raspberry Pi 5 (8GB RAM Single Board Computer)         |  |
         |  +---------------------------|----------------------------+  |
         |                              | PCIe FPC Cable Link           |
         |  +---------------------------v----------------------------+  |
         |  | Pineberry Pi HAT+ NVMe SSD Shield                      |  |
         |  |  +--------------------------------------------------+  |  |
         |  |  | 256GB Kingston Industrial M.2 NVMe SSD (X-7R)    |  |  |
         |  |  +--------------------------------------------------+  |  |
         |  +--------------------------------------------------------+  |
         |                                                              |
         |  +------------------------+      +------------------------+  |
         |  | Mornsun 12V-to-5V 5A   |      | Integrated Solid       |  |
         |  | DC-DC Buck Converter   |      | Copper Heat Block      |  |
         |  +------------------------+      +------------------------+  |
         +--------------------------------------------------------------+
```

### 3. Sourcing Specifications & Connector Sizing Schedule
Vetted components for the base station gateway build are detailed below:

| Component / Sub-Assembly | Vetted Part Number | Chinese Factory Manufacturer | Function / Description |
| :--- | :--- | :--- | :--- |
| **SBC Computer** | Raspberry Pi 5 (8GB) | Raspberry Pi Foundation | Primary processing unit running Node-RED & sync scripts. |
| **LoRa Concentrator** | RAK5146-SPI-915 | RAKwireless Technology | Multi-channel LoRa concentrator HAT (polls 8 channels). |
| **NVMe SSD Shield** | Pineberry Pi Hat+ | Pineberry Pi / Geekworm | PCIe Gen 2/3 NVMe interface board. |
| **Storage Medium** | Kingston DC1000B 240GB | Kingston / LCSC | Industrial-grade high-TBW NVMe M.2 SSD. |
| **Power Supply** | Mornsun K7805-500R3 | Mornsun Shenzhen | High-efficiency 12V-to-5V DC-DC buck converter. |
| **Chassis** | AK-C-B80 (120x97x40mm) | Shenzhen SZOMK | Heavy extruded aluminum chassis w/ flanged end-plates. |
| **Antenna Bulkheads** | IPEX-1 to RP-SMA-K | Shenzhen Ebyte | RG178 coaxial pigtail bulkheads with locking nuts. |
| **Waterproof Glands** | PG7 Brass Gland | Yueqing Liron | Brass nickel-plated compression glands for power/LAN. |

### 4. Thermal Management & Port Interface Details
*   **Passive Conduction Cooling**: The aluminum enclosure features customized internal mounting standoffs and a **solid copper thermal block (15mm x 15mm x 6.5mm)** that directly bridges the Raspberry Pi 5 Broadcom BCM2712 CPU with the heavy aluminum chassis wall. This acts as a giant heatsink, maintaining CPU temps below 113°F (45°C) even under maximum load in hot summer cabin attics.
*   **External Connectors Layout**:
    *   *Side A (Flanged End Plate)*:
        *   Two **RP-SMA female bulkhead connectors** for external high-gain antennas (one tuned to 915 MHz LoRa, one for 2.4 GHz WiFi).
        *   One **PG7 brass gland** feeding the 12V/24V DC input cable from the cabin solar battery bank.
    *   *Side B (Flanged End Plate)*:
        *   One waterproof **RJ45 bulkhead connector (IP67 plastic coupling)** providing a secure, sealed local area network (LAN) port for field debugging or wired cabin network connection.
        *   Laser-etched status LED indicators (Power, LoRa Rx/Tx, internet status).
*   **Power Distribution**: The Mornsun buck regulator steps down the variable 12V–24V DC battery line to a stable 5.0V (up to 5A) routed directly to the Pi's power test pads (pins 2 and 4), bypassing the fragile USB-C connector. A built-in transient voltage suppressor (TVS) diode (LCSC **SMBJ5.0A**) protects the computer from power surges caused by lightning strikes on high tower antennas.

---
*Developed by Blue Ridge Stream Restoration Technical Sourcing Operations. Pushed to remote origin under main.*
