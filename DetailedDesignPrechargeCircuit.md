# Detailed Design: Precharge Circuit

This document delineates the objectives of a comprehensive system design. Upon reviewing this design, the reader should have a clear understanding of:

- How the specific subsystem integrates within the broader solution
- The constraints and specifications relevant to the subsystem
- The rationale behind each crucial design decision
- The procedure for constructing the solution


## General Requirements for the Document

The document should include:

- Explanation of the subsystem’s integration within the overall solution
- Detailed specifications and constraints specific to the subsystem
- Synopsis of the suggested solution
- Interfaces to other subsystems
- 3D models of customized mechanical elements*
- A buildable diagram*
- A Printed Circuit Board (PCB) design layout*
- An operational flowchart*
- A comprehensive Bill of Materials (BOM)
- Analysis of crucial design decisions

*Note: These technical documentation elements are mandatory only when relevant to the particular subsystem.


## Function of the Subsystem

A precharge circuit is a key safety feature in high-voltage electric vehicles like those used in Formula SAE Electric (FSAE) 
competitions. When the car is first powered on, components like the motor controller have large capacitors that initially act 
like a short circuit. If full voltage is applied all at once, it can cause a huge surge of current—damaging components, welding 
shut contactors, or even creating dangerous sparks. A precharge circuit prevents this by temporarily routing power through a 
resistor, allowing the capacitors to charge gradually. Once the voltage levels out, the main contactor closes to supply full 
power, and the resistor is bypassed. This simple system protects vital electronics, extends component life, and ensures the car 
meets FSAE safety rules.


## Specifications and Constraints

   ### Specifications
   
   - The precharge circuit shall limit the inrush current to less than 5 A during the capacitor charging phase.

   - The precharge relay shall be energized only when the BMS reports a no-fault condition and the high-voltage interlock 
     loop is closed.

   - The precharge circuit shall measure motor controller voltage to determine when the system is sufficiently charged 
     (≥90% of pack voltage).

   - The main contactor shall close only after the precharge voltage condition has been met.

   - The precharge resistor shall be rated for a minimum of 225 W continuous and sufficient pulse energy to handle full 
     charge-up events.

   - The system shall open the precharge relay immediately after the main contactor is closed to prevent overheating of 
     the resistor.
      
   ### Constraints

1. The Precharge Circuit shall: [11]

   - Be able to charge the Intermediate Circuit to minimum 90% of the Accumulator voltage before closing the second IR 
         [11]
   
   - Be supplied from the Shutdown Circuit EV.7.1 [11]
   
   - The Accumulator shall contain a Precharge Circuit. EV.5.6.1 [11]

   - Positive Temperature Coefficient (PTC) devices shall not be used to limit current for the Precharge Circuit 
         EV.5.6.4 [11]

   - The precharge relay shall be a mechanical type relay EV.5.6.5 [11]


## Overview of Proposed Solution

This precharge circuit is designed to safely energize the high-voltage system in a Formula SAE Electric vehicle using an Orion BMS 2 and a modular lithium-ion battery pack. Its primary function is to protect components like the motor controller from harmful inrush currents when the system is first powered on.

The circuit includes a 100 Ω, 225 W Ohmite resistor to limit inrush current, controlled by a TE EV200AAANA relay during the precharge phase. Once the system voltage reaches about 90% of the battery voltage, a Gigavac GV200MDA main contactor closes to deliver full power and bypass the resistor.

A voltage divider connected to a Teensy microcontroller monitors the voltage across the motor controller to determine when precharge is complete. The system can also receive input from the Orion BMS, which provides key data such as pack voltage, precharge control signals, and fault status—either through digital I/O or over the CAN bus.

This solution works seamlessly with the Orion BMS 2, ensures the precharge process runs automatically every time the vehicle powers up, and complies with FSAE Electric rules. It offers a safe, reliable, and easy-to-integrate method for managing high-voltage startup in an electric race car.


## Interface with Other Subsystems

### Inputs to the Precharge Circuit

 #### From Orion BMS 2:
  - Precharge FET Enable (Digital Output): Signals when precharge is permitted.
    
  - Pack Voltage (CAN Data): Used to compare with controller voltage to determine precharge completion.
    
  - Fault Status (Digital Output or CAN): Indicates critical issues (e.g., overvoltage, undervoltage, overtemperature).
    
  - High Voltage Present (Digital Output or CAN): Confirms pack is live and ready.
    
 #### From Vehicle or Driver Controller:
 
  - HV Enable Switch (Digital Input): Activates the HV system manually from the driver or shutdown circuit.
    
  - Safety Interlock Loop (Digital Input): Series-wired safety switches (e.g., TSMS, IMD, inertia switch) must be closed 
    to proceed.
    
 #### From Precharge Voltage Sensing:
 
  - Motor Controller Voltage (Analog Input via Voltage Divider): Monitored by a microcontroller to assess precharge 
    progress.

### Outputs From the Precharge Circuit

 #### To Actuators: 
 
  - Precharge Relay Control (Digital Output, 12 V): Closes the precharge relay to begin charging the controller capacitors.
    
  - Main Contactor Control (Digital Output, 12 V): Closes the main contactor after precharge is complete.
    
 #### To Orion BMS 2:
 
  - Precharge Complete Feedback (Digital Input or CAN): Optional status signal showing successful precharge.
    
 #### To Driver/Interface:
 
  - Precharge Status Indicator (Digital Output or CAN): Indicates current state (precharging, complete, or fault) on 
    dashboard or logging system.
    
## 3D Model of Custom Mechanical Components

<img width="600" alt="3D_Drawing" src="https://github.com/user-attachments/assets/7b958ffc-730d-46b8-90ab-472bfc7ec6f5" />

This image shows the key components of a precharge circuit used in electric vehicles, like a Formula SAE car. It includes a large green resistor (used to limit inrush current), a pair of high-voltage contactors (which control power flow), and a simple wiring layout that connects everything. The resistor allows the motor controller to charge up slowly before the main contactor closes, preventing damage. The diagram offers a clean visual of how the parts fit together and helps with planning wiring and mounting in a real system.

## Buildable Schematic 

Integrate a buildable electrical schematic directly into the document. If the diagram is unreadable or improperly scaled, the supervisor will deny approval. Divide the diagram into sections if the text and components seem too small.

The schematic should be relevant to the design and provide ample details necessary for constructing the model. It must be comprehensive so that someone, with no prior knowledge of the design, can easily understand it. Each related component's value and measurement should be clearly mentioned.


## Printed Circuit Board Layout

Include a manufacturable printed circuit board layout.


## Flowchart

For sections including a software component, produce a chart that demonstrates the decision-making process of the microcontroller. It should provide an overview of the device's function without exhaustive detail.


## BOM

Provide a comprehensive list of all necessary components along with their prices and the total cost of the subsystem. This information should be presented in a tabular format, complete with the manufacturer, part number, distributor, distributor part number, quantity, price, and purchasing website URL. If the component is included in your schematic diagram, ensure inclusion of the component name on the BOM (i.e R1, C45, U4).
| **Item** | **Component**              | **Part Number / Model**     | **Description**                                       | **Specification**                | **Estimated Price (USD)** | **Source / Manufacturer** |
| -------- | -------------------------- | --------------------------- | ----------------------------------------------------- | -------------------------------- | ------------------------- | ------------------------- |
| 1        | Precharge Resistor         | Ohmite L225J100E            | Chassis-mount wirewound resistor                      | 100 Ω, 225 W, 5%                 | \$37.20                   | Ohmite                    |
| 2        | Precharge Relay            | TE EV200AAANA               | DC contactor for low-current precharge path           | 900 VDC, 15 A, 12 V coil         | \$80.00                   | TE Connectivity           |
| 3        | Main Contactor             | Gigavac GV200MA-1           | Sealed contactor for main high-voltage connection     | 900 VDC, 400 A, 12 V coil        | \$145.00                  | Sensata / Gigavac         |
| 4        | Microcontroller (optional) | Teensy 4.0                  | For control logic and voltage sensing                 | 32-bit, CAN, ADC                 | \$25.45                   | PJRC                      |
| 5        | Voltage Divider Resistors  | Vishay VR68 series          | High-voltage resistors for analog voltage measurement | 1 MΩ and 12 kΩ, 350+ V rated     | \$2.34                    | Vishay / Mouser           |
| 6        | Precharge Harness Wire     | TXL-22                      | High-voltage rated automotive wire                    | 22 AWG, 600 V rated              | \$1.28 (20 ft)            | Prowire USA               |
| 7        | Relay Connector Housing    | AMPSEAL 3-pin               | Connector for EV200 relay coil terminals              | Crimp contacts and housing       | \$16.95                   | TE Connectivity / eBay    |
| 8        | Contact Boots / Insulation | HellermannTyton MS3109-06AU | Rubber boots for HV terminals                         | 6 pcs, ≥150 VDC                  | \$35.00                   | HellermannTyton / eBay    |
| 9        | Mounting Hardware          | M4 Bolts + Washers          | For mounting resistor, relays, contactors             | Stainless steel M4–M6 hardware   | \$1.10 (5 pieces)         | McMaster / Local          |
| 10       | Heatshrink Tubing          | 3M Dual Wall                | For insulating HV terminations                        | 3:1 shrink ratio, adhesive-lined | \$2.49                    | 3M / Sherco Auto          |


## Analysis

The presented precharge circuit design incorporates key components including a 100 Ω, 225 W Ohmite resistor, a TE Connectivity EV200AAANA relay, and a Gigavac GV200 series main contactor, integrated under the control of an Orion BMS 2. This configuration effectively meets the operational, safety, and regulatory constraints required for a Formula SAE Electric vehicle operating at 102 V nominal and 6.3 kWh capacity.

### Functionality and System Behavior

At power-up, motor controllers present a near-short circuit due to their large DC link capacitors. If the main contactor were closed immediately, a damaging inrush current—on the order of hundreds of amps—would flow. The precharge resistor solves this by temporarily introducing resistance in the HV path, reducing the initial current spike.

Using Ohm’s Law: V = I / R = 102V / 100 ohms = 1.02 Amperes

This current is well below the 5 A inrush limit typical for automotive-grade relays and minimizes stress on both the contactor and motor controller. The Ohmite L225J100E can handle high surge energy, making it suitable for repeated precharge events during competition use.

The system's logic—either handled directly by the Orion BMS 2’s digital outputs or via an external microcontroller using CAN telemetry—ensures that the main contactor closes only when the voltage across the controller reaches ~90% of pack voltage. This confirms capacitor charge completion and protects against premature switching.

### Compliance With System Constraints

1. Electrical Ratings:
   
   - All components (relay, contactor, resistor) are rated well above the system’s 102 V operating voltage.
     
   - The Gigavac GV200 series contactor and TE EV200 relay support up to 900 VDC, providing ample headroom for transient 
     conditions and future upgrades.

2. FSAE Electric Compliance

   - FSAE EV rules (e.g., EV4.6.x) require automatic precharge at each HV enable event and ensure that the main contactor 
     does not close until precharge is complete. This design supports both requirements.

   - Safety interlock (TSMS, IMD, brake switch) integration is supported via digital I/O.
  
   - Discharge on shutdown is supported through the main contactor path (if paired with a resistive discharge path or BMS- 
     controlled discharge FETs), complying with the <60 V in 5 s rule.

### Thermal and Reliability Considerations

The precharge resistor’s peak energy during a full precharge is: E = {1/2) * C * V^2
Assuming DC link capacitance of 1,000 μF: E = 0.5 * 0.001 * 102^2
The Ohmite resistor’s ceramic enclosure and 225 W continuous rating far exceed this transient energy, ensuring long life and tolerance to frequent cycling.

The EV200 relay and GV200 contactor are hermetically sealed and vibration-resistant, designed specifically for electric vehicle applications. Their long cycle life and robust isolation reduce the risk of arc faults or welding under high load conditions.

### Mechanical Fit and Maintainability

As shown in the associated CAD image, the components are compact, bolt-mountable, and easily routed. The image also offers a wiring example that simplifies implementation in an accumulator enclosure or HV distribution box. The modularity of the design enables easy diagnostics, replacement, and expansion (e.g., adding discharge circuitry or auxiliary contact monitoring).

## References

[1] Ohmite Manufacturing Company, 270 Series Wirewound Resistors - L225J100E Datasheet, Ohmite, 2023. [Online]. Available: https://www.ohmite.com/catalog/270-series/L225J100E

[2] TE Connectivity, EV200AAANA DC Contactor – Product Specification Sheet, TE Connectivity Ltd., 2023. [Online]. Available: https://www.te.com/en/product-1618002-7.html

[3] Sensata Technologies, GV200 Series Sealed Power Contactors – Datasheet, Sensata Gigavac, 2023. [Online]. Available: https://www.sensata.com/sites/default/files/a/sensata-gigavac-gv200-series-open-contactors-datasheet.pdf

[4] Ewert Energy Systems, Orion BMS 2 Operational Manual, OrionBMS.com, Revision 3.3, 2023. [Online]. Available: https://www.orionbms.com/manuals/pdf/orionbms2_operational_manual.pdf
