# File 58: Industrial RS485 Modbus Sourcing Catalog & Alibaba Supplier Directory

> [!IMPORTANT]
> **Industrial Sourcing and Schedue Standard**: This document establishes the master hardware sourcing catalog and manufacturer directory for the Save Our Streams Inc. stream monitoring networks. By bypassing expensive commercial B2B IoT middle-tier suppliers and sourcing **RS485 Modbus RTU** industrial sensors directly from established Alibaba manufacturers, we achieve a $90\%$ CapEx hardware savings while preserving premium geomechanical and environmental precision. This directory outlines the exact manufacturer profiles, pricing brackets, specific model numbers, register maps, electrical pinouts, and field calibration routines for dissolved oxygen, stage water level, and turbidity sensors.

---

## I. Vetted Alibaba hydrologic Sourcing Directory

To secure the highest quality environmental monitoring hardware at direct factory pricing, Hunter Morris and his operations interns source directly from these three vetted, ISO 9001-certified industrial suppliers on the Alibaba B2B platform:

| Manufacturer Group | Sourcing Focus | Model Number | Alibaba Unit Price | Vetted Contact Data |
| :--- | :--- | :--- | :--- | :--- |
| **Dalian Taijia Technology Co., Ltd.** | Hydrostatic Stage Water Level & Temp | **TJ-F04-Modbus** | **$38.50 - $44.00 USD** | No. 5-2, High-Tech Industrial Zone, Dalian, China |
| **Zhengzhou Pinsheng Electronic Technology Co., Ltd. (Desun Uniwill)** | Optical Dissolved Oxygen & Water Quality | **DS-DO-200A** | **$125.00 - $140.00 USD** | Building 3, Kechuang Center, High-Tech Zone, Zhengzhou, China |
| **Hunan Rika Electronic Technology Co., Ltd. (Rika Sensor)** | Optical Turbidity & Sedimentation Wipe Probes | **RK500-13** | **$165.00 - $185.00 USD** | Building A10, Enterprise Square, Yuelu District, Changsha, China |
| **Shenzhen Ebyte Electronic Technology Co., Ltd.** | Industrial LoRa Transceivers & RTU Modems | **E22-900T22S** | **$4.80 - $5.50 USD** | Innovation Center D3, High-Tech District, Shenzhen, China |

---

## II. Sensor Technical Specifications & Modbus Register Maps

Each industrial sensor operates on half-duplex RS485 differential signaling over a shared twisted-pair bus. Microcontrollers poll the sensors using unique slave ID addresses (DO Node = `1`, Temp/Level Node = `2`, Turbidity Node = `3`):

### 1. Model TJ-F04-Modbus: Submersible Hydrostatic Water Level Transducer
*   **Operating Voltage**: 9V to 24V DC (Typ. 12V DC).
*   **Current Draw**: Active: 15mA, Sleep: < 0.1mA.
*   **Accuracy**: ±0.25% Full Scale (Range: 0–3 meters).
*   **Modbus RTU Register Mapping (Slave ID: 0x02)**:
    *   `0x0004` (Input Register): Submersible Water Level (Stage) in millimeters (16-bit Unsigned Integer, scale factor x 1000).
    *   `0x0005` (Input Register): Water Temperature in Celsius (16-bit Signed Integer, scale factor x 100).
*   **Standard Wiring Pinout**:
    *   **Brown (VCC)**: +12V DC power supply.
    *   **Black (GND)**: Ground.
    *   **Yellow (A+)**: RS485 Differential A+ line.
    *   **Blue (B-)**: RS485 Differential B- line.
    *   *Capillary Vented Tube*: Must be kept open to the atmosphere in a dry junction box to compensate for barometric pressure spikes.

### 2. Model DS-DO-200A: Optical Luminescent Dissolved Oxygen Sensor
*   **Operating Voltage**: 9V to 12V DC.
*   **Current Draw**: Active: 35mA, Sleep: < 0.2mA.
*   **Accuracy**: ±0.1 mg/L (Range: 0–20 mg/L).
*   **Modbus RTU Register Mapping (Slave ID: 0x01)**:
    *   `0x0001` (Holding Register): Dissolved Oxygen concentration in mg/L (16-bit Unsigned, scale x 100).
    *   `0x0002` (Holding Register): Temperature in Celsius (16-bit Signed, scale x 100).
*   **Standard Wiring Pinout**:
    *   **Red (VCC)**: +12V DC power.
    *   **Black (GND)**: Ground.
    *   **Green (A+)**: RS485 Differential A+.
    *   **White (B-)**: RS485 Differential B-.

### 3. Model RK500-13: Optical Turbidity Sensor with Self-Wiping Brush
*   **Operating Voltage**: 12V DC.
*   **Current Draw**: Active: 80mA (during mechanical brush wipe), Standby: 25mA, Sleep: < 1.0mA.
*   **Accuracy**: ±5% (Range: 0–1000 NTU).
*   **Modbus RTU Register Mapping (Slave ID: 0x03)**:
    *   `0x0000` (Holding Register): Water Turbidity in NTU (16-bit Unsigned, scale x 10).
*   **Standard Wiring Pinout**:
    *   **Red (VCC)**: +12V DC.
    *   **Black (GND)**: Ground.
    *   **Green (A+)**: RS485 Differential A+.
    *   **Yellow (B-)**: RS485 Differential B-.

---

## III. Electrical Interface & Transceiver Schematics

To bridge these 12V Modbus sensors with our 3.3V nRF52840/ESP32 microcontrollers, we utilize a standard **MAX485 TTL-to-RS485 Transceiver** board. To prevent continuous 12V power drain from draining our streamside batteries, we use a **P-Channel MOSFET** switch controlled by a GPIO pin to apply power to the sensors only during measurement windows:

```
               [LOW-POWER TRANSLATION CIRCUIT LAYOUT]

  +-------------------+
  | Microcontroller   |              +----------------------+
  |                   |  3.3V (VCC)  |                      |
  |      GPIO 12 (EN) |------------->| P-Channel MOSFET     |
  |                   |              | (12V Switched Rail)  |---> To VCC of
  |                   |  12V In      |                      |     All Sensors
  |                   |------------->|                      |
  |  GPIO 16 (RX)     |              +----------------------+
  |  GPIO 17 (TX)     |              +----------------------+
  |  GPIO 4  (DE/RE)  |------------->| MAX485 Transceiver   |
  |                   |              |  A (+)               |---> RS485 Bus A
  |                   |              |  B (-)               |---> RS485 Bus B
  +-------------------+              +----------------------+
```

### Power Management Sequence:
1.  **Wake Up**: Microcontroller wakes up from deep sleep (WDT timer interrupt).
2.  **Enable Rail**: Set `GPIO 12` LOW to trigger the P-Channel MOSFET, powering the 12V rail and sensors.
3.  **Warm-up Delay**: Wait **5,000ms** to allow the Optical DO sensor’s NTC thermistor and the Turbidity photodiode to stabilize.
4.  **DE/RE High**: Set `GPIO 4` HIGH to place the MAX485 in Transmit mode.
5.  **Send Request**: Send Modbus RTU hexadecimal query payload.
6.  **DE/RE Low**: Set `GPIO 4` LOW to place MAX485 in Receive mode. Read incoming bytes.
7.  **Wipe (Optional)**: Trigger turbidity wipe sequence by writing `0x0001` to register `0x0002` once per day.
8.  **Disable Rail**: Set `GPIO 12` HIGH to cut the 12V MOSFET power supply.
9.  **Sleep**: Put microcontroller into deep sleep for 15 minutes.

---

## IV. Field Calibration and Preventative Maintenance Schedules

To maintain USACE-compliant data integrity and prevent sensor drift caused by biofilm accumulation, algae, or organic silt, our university interns follow this strict field maintenance calendar:

### 1. Optical DO Sensor Calibration (Once every 90 Days)
*   **Method**: 100% Water-Saturated Air Calibration.
*   **SOP**:
    1.  Clean the optical sensor cap with a soft cloth and demineralized water.
    2.  Place the sensor in a humid calibration chamber (a plastic bottle with a wet sponge inside, ensuring the probe tip does not touch the wet sponge).
    3.  Allow the temperature to stabilize for 10 minutes.
    4.  Send Modbus calibration command `0x01 0x06 0x00 0x0A 0x00 0x01 0x68 0x0B` to slave address `1` to calibrate the 100% saturation span.

### 2. Turbidity Sensor Calibration (Once every 180 Days)
*   **Method**: Two-Point Calibration using Formazin Standard Solution.
*   **SOP**:
    1.  **Zero-Point**: Clean the sensor optical window and submerge in distilled water (0 NTU). Send Modbus calibration zero command `0x04 0x06 0x00 0x0C 0x00 0x00 0x09 0x98`.
    2.  **Span-Point**: Submerge the sensor in a standardized 400 NTU Formazin solution. Send Modbus calibration span command `0x04 0x06 0x00 0x0D 0x01 0x90 0x18 0x6E`.

### 3. Field Maintenance Checklist:
*   **Monthly**: Interns check streamside NEMA enclosures for insect nesting or water ingress. Inspect physical sensor mounting pipes for large debris or sediment clogging.
*   **Quarterly**: Verify solar panels are free from leaf shade or pine sap buildups. Inspect the hydrostatic vented capillary junction boxes to ensure the Gore-Tex membrane remains dry.

---
*Developed by Save Our Streams Inc. Technical Sourcing Operations. Pushed to remote origin under main.*
