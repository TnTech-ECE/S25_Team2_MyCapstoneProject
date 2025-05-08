# Accumulator Container Subsystem

**FSAE Electric Capstone Team**  
*Mackenzie Raleigh*

---

## Subsystem Integration Overview

The accumulator enclosure is a central Formula SAE Electric vehicle subsystem tasked with housing the main energy source: ~60–70 Molicel P42A lithium-ion battery cells. It gives structural, thermal, and electrical safety features in addition to integrating with the overall high-voltage powertrain. It connects to the battery management system (BMS), vehicle telemetry, safety interlocks, and power distribution units. The container provides mechanical rigidity, vibration protection, environmental protection, and EV5.3 through EV5.8 rule compliance according to the FSAE Electric rulebook.

---

## Specifications and Constraints

### Key Specification (based on Enepaq P42A datasheet)

- **Battery module**: Enepaq Li1x10pP42A  
- **Rated Voltage**: 42V per module  
- **Capacity**: 151.2 Wh  
- **Discharge current**: 45A continuous, 84A peak  
- **Temperature Range**:
  - Discharge: -40°C to +60°C
  - Charge: 0°C to +60°C  
- **Integrated Protections**:
  - Dual fuses per cell
  - Flame-rated plastics (UL94 V-0)
  - Dedicated gas venting channels
  - Built-in temperature sensors (100% coverage)
- **Ingress Protection Target**: IP55 via enclosure

### Constraints

- **FSAE Rule Compliance**: Shall be EV5.3–EV5.8  
- **Ethical/Safety Constraint**: It shall reduce thermal runaway and fire risks for student operators.  
- **Social/Economic Constraint**: Shall target cost-efficiency with justifiable performance and safety budget.  
- **Standards Constraint**: Shall be UL94-V0 fire-retardant enclosure; voltage isolation >120V.  

**Reference**: Enepaq Datasheet Rev. E (2024-12-05)

---

## Proposed Solution Synopsis

The proposed setup pairs two Enepaq Li1x10pP42A modules (42V each) into an Altelix 17x14x6” PC + ABS enclosure. The enclosure provides plenty of space, flame resistance, and IP55-rated weatherproofing. The following modifications are made: 

- Factory AC ports replaced with Heyco DC grommets  
- Internal lining with Nomex sheet or FR4 for enhanced flame insulation  
- Adding vent ports and pressure relief valves for EV5.8 compliance  
- Mounting 3D-printed module brackets and foam dampening supports  
- Integration of Kapton-wrapped bus bars and the Orion BMS 2  
- Sensor interfacing with Orion BMS 2’s thermistor inputs

**Product links**:
- [Altelix Enclosure](https://altelix.com/altelix-17x14x6-pc-abs-weatherproof-nema-enclosure-with-hinged-door-aluminum-mounting-plate/)
- [Enepaq Modules](https://www.enepaq.com)
- [Orion BMS 2](https://www.orionbms.com/products/orion-bms-standard/)

---

## Interface with Other Subsystems

| Interface         | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Power Bus**     | Outputs ~120V DC to inverter, connected via insulated XT90 connectors       |
| **BMS Interface** | Reports cell voltages and temperatures via CAN, UART, or thermistor signals |
| **Vehicle Telemetry** | Transfers Orion BMS data to telemetry systems for monitoring and logging |
| **Safety Circuit**   | Accepts fault signals from BMS shutdown or fuse detection circuits        |

---

## 3D Model of Mechanical Components

![image](https://github.com/user-attachments/assets/9b68364e-eec9-4507-a12c-b5ed0a5af9fe)

Specialized mechanical components were developed for installation, serviceability, and safety. The battery cell holders printed via 3D are designed for precise fitting and protection from vibration. The snap-fit structures and inherent channels within the holders ensure insulation and thermal barrier routing. Nomex insulation sheets, developed as interior lining panels, were produced to match the size of the container while maintaining flame retardancy. Furthermore, ventilation adapters are CAD-modeled to include waterproof vent ports with pressure relief. Exploded views expose the layering methods of cells, insulation, busbars, and sensors, for readability and modularity. All CAD designs are dimensioned, and 3D print tested for compatibility.  

- 3D-Printed Holders: These holders secure modules and incorporate shock absorption features.
- Nomex Paneling Layout: Exploded view model showing interior flame shield zones.
- Ventilation Inserts: CAD-designed adapter rings for IP-rated exhaust vents.

---

## Buildable Electrical Schematic

![image](https://github.com/user-attachments/assets/8b441499-4985-4eac-9217-d3efa9baf6c1)


The electrical schematic was created to simulate a high-voltage accumulator subsystem in compliance with Formula SAE specifications. The circuit is made up of two Enepaq modules in series to deliver ~120V DC. Both modules are interfaced to the Orion BMS 2 through single cell voltage taps and temperature sensors. The schematic includes inline fuses on the output, a Manual Service disconnect (MSD), and safety relays powered by the Orion BMS fault output. Connectors are labeled, and wire gauges are selected to accommodate peak discharge currents. The schematic is grouped into logical sets: battery module interconnects, BMS integration, safety control, and system output. The entire diagram is being finalized in CAD, with design rules to guarantee trace width, voltage clearance, and thermal performance standards. Reference symbols follow the IPC-2221, which is defing a multitude of PCB design aspects, and manufacturer datasheet conventions.  

The schematic simulates a high-voltage system compliant with Formula SAE specs. It includes:

- Two Enepaq modules wired in series (~120V DC)
- Orion BMS 2 with cell taps and thermistors
- Inline Littelfuse 30A fuses
- Manual Service Disconnect (MSD)
- Relays driven by Orion BMS fault outputs

Logical groups in the schematic include: module interconnects, BMS integration, safety relays, and power output. Design rules follow IPC-2221 and manufacturer conventions.

---

## PCB Layout

![image](https://github.com/user-attachments/assets/2eaf5e83-8a52-40ce-9cd3-29f30bf057d9)


A custom 4-layer PCB is being designed to house the Orion BMS 2 interface circuitry. The design includes high-precision traces for voltage taps, analog temperature sensor routing, and CAN/UART communication lines. Layers are divided into ground, signal, and high-voltage nets with isolation distances to IPC-2221 for operation at 120V DC. The top layer includes thermistor signals from JST XH headers routed to the Orion connector. Middle layers provide shielding and power/ground distribution, and the bottom layer contains the CAN transceiver and diagnostics ports. Components are surface mounted and routed to minimize noise and facilitate serviceability. Sizing is for fit in available enclosure panel space, and thermal reliefs are included to radiate local heating. Mounting holes are positioned for direct fit into the Altelix aluminum backplate, offering secure, isolated mounting.  

A custom 4-layer PCB routes:

- Voltage taps
- Analog temperature sensors
- CAN/UART data lines

Each layer serves specific nets (ground, signal, HV), with IPC-compliant clearance for 120V. Surface-mounted parts reduce noise and optimize layout. Mounting holes align with Altelix backplate.

---

## Operational Flowchart

![image](https://github.com/user-attachments/assets/51a99a9a-9b48-42ec-8cbe-a6dd04a6c830)

The accumulator subsystem follows a specific operational sequence to ensure safety and performance. Upon power-up, the system initializes and reads voltage and temperature data from the Orion BMS. If all values are within safe limits, the system enables the high-voltage output and begins logging to the vehicle telemetry system. Continuous monitoring is performed during operation, and in the event of a fault such as over-temperature or voltage imbalance, the Orion BMS triggers a system shutdown to prevent damage or hazards.  

---

## Bill of Materials

| Component            | Ref. | Qty | Manufacturer   | Part Number    | Distributor   | Price   |
|---------------------|------|-----|----------------|----------------|---------------|---------|
| Altelix Enclosure   | ENC1 | 1   | Altelix        | NX171406       | Altelix       | $72     |
| Molicel P42A Module | BATT | 2   | Enepaq         | Li1x10pP42A    | Enepaq        | $60 x2  |
| Nomex Sheet         | INS1 | 1   | DuPont         | Nomex Type 410 | McMaster      | $25     |
| DC Grommets         | G1   | 4   | Heyco          | RDD-125        | Digi-Key      | $4.50   |
| Vent Port           | VP1  | 1   | Littelfuse     | 0ZCJ Series    | Mouser        | $8.00   |
| Orion BMS 2         | BMS1 | 1   | Ewert Energy   | Orion BMS 2    | OrionBMS.com  | $820    |
| Kapton Tape         | CT1  | 1   | 3M             | 5413           | Digi-Key      | $12     |
| Inline Fuses        | F1   | 2   | Littelfuse     | 0AFH030.Z      | Mouser        | $3.00   |

**Estimated Total**: ~$1,044 (subject to adjustment based on sourcing and volume pricing)

---

## Design Decision Analysis

- **Safety**:The Enepaq modules include dual-layer protection while the Orion BMS manages fault detection, temperature regulation, and telemetry.  
-**Spatial Efficiency**: The Altelix enclosure provides adequate internal space for components while allowing for insulation and airflow. 
-**Integration Simplicity**: The Orion BMS accommodates thermistors, voltage sensing, and CAN communication in a single package.  
-**Regulatory Compliance**: The solution exceeds EV5.3-EV5.8 standards through its flame-resistant build and comprehensive monitoring.  
-**Cost-Benefit Balance**: Although premium in price, the Orion BMS’s features, and dependability justify its inclusion.   Dual-layer protection in modules; Orion BMS fault monitoring  

---

## References

[1] Enepaq, “Li1xNpP42A Datasheet, Revision E,” Dec. 2024. [Online]. Available: https://www.enepaq.com 

[2] SAE International, “Formula SAE Electric Rules 2025.” [Online]. Available: https://www.sae.org 

[3] Altelix, “NX171406 Enclosure Product Sheet.” [Online]. Available: https://altelix.com 

[4] Ewert Energy Systems, “Orion BMS 2 Specifications.” [Online]. Available: https://www.orionbms.com/downloads/documents/orionbms2_specifications.pdf 

[5] IPC, “IPC-2221: Generic Standard on Printed Board Design.” [Online]. Available: https://www.ipc.org 

[6] UL, “UL94: Standard for Safety of Flammability of Plastic Materials for Parts in Devices and Appliances.” [Online]. Available: https://www.ul.com 

[7] Ewert Energy Systems, “Orion BMS CAN Protocol Guide.” [Online]. Available: https://www.orionbms.com 

