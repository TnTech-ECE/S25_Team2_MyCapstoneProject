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

![image](https://github.com/user-attachments/assets/dcabd75c-e069-4de2-be98-c02c300a3e6e)

This schematic illustrates a precharge circuit for a high-voltage EV system, designed to safely charge the motor controller's input capacitors before the main contactor (K2) closes. At power-up, the high-voltage supply passes through a precharge resistor (R1) and a precharge relay (K1), limiting inrush current to the motor controller. A microcontroller (U1) monitors voltage via a divider formed by resistors R2 and R3. Once the sensed voltage reaches approximately 90% of the pack voltage, U1 deactivates K1 and activates K2, closing the full-current path.

## Printed Circuit Board Layout

![image](https://github.com/user-attachments/assets/2bfd4462-17fc-4d81-8496-ff1772a0ec5a)



## Flowchart

![image](https://github.com/user-attachments/assets/f9127d88-69c0-43b0-bbfe-ee305400b1ef)



## BOM

| **Designator** | **Component**              | **Manufacturer** | **Manufacturer Part Number** | **Distributor** | **Distributor Part Number** | **Quantity** | **Unit Price (USD)** | **Total Price (USD)** | **Purchase URL**                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------- | -------------------------- | ---------------- | ---------------------------- | --------------- | --------------------------- | ------------ | -------------------- | --------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| R1             | Precharge Resistor         | Ohmite           | L225J100E                    | Digi-Key        | 273-L225J100E-ND            | 1            | \$37.20              | \$37.20               | [Link](https://www.digikey.com/en/products/detail/ohmite/L225J100E/823557)           |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| K1             | Precharge Relay            | TE Connectivity  | EV200AAANA                   | Mouser          | 655-EV200AAANA              | 1            | \$80.00              | \$80.00               | [Link](https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA)      |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| K2             | Main Contactor             | Gigavac          | GV200MA-1                    | Mouser          | 682-GV200MA-1               | 1            | \$145.00             | \$145.00              | [Link](https://www.mouser.com/ProductDetail/GIGAVAC/GV200MA-1)                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| U1             | Microcontroller (Optional) | PJRC             | Teensy 4.0                   | PJRC            | TEENSY40                    | 1            | \$26.80              | \$26.80               | [Link](https://www.pjrc.com/store/teensy40.html)                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| R2, R3         | Voltage Divider Resistors  | Vishay           | VR68000003303JAC00           | RS Components   | 70397223                    | 2            | \$0.80               | \$1.60                | [Link](https://us.rs-online.com/product/vishay-dale/vr68000003305jac00/70397223/)    |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| W1             | Precharge Harness Wire     | Southwire        | TXL22-4                      | IEWC            | TXL22-4                     | 20 ft        | \$0.10/ft            | \$2.00                | [Link](https://www.iewc.com/product/txl22-4)                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| J1             | Relay Connector Housing    | TE Connectivity  | 776523-3                     | TE Connectivity | 776523-3                    | 1            | \$1.50               | \$1.50                | [Link](https://www.te.com/en/product-776523-3.html)                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| B1             | Contact Boots/Insulation   | HellermannTyton  | MS3109-06AU                  | PEI-Genesis     | MS3109-06AU                 | 2            | \$5.00               | \$10.00               | [Link](https://www.peigenesis.com/en/shop/f/MS3109.html)                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| HW1            | Mounting Hardware          | Generic          | M4 x 20mm SS Bolt            | Accu Components | SEBF-M4-20-A2               | 5            | \$0.22               | \$1.10                | [Link](https://accu-components.com/us/full-thread-hexagon-bolts/18823-SEBF-M4-20-A2) |                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| HS1            | Heatshrink Tubing          | 3M               | EPS-300-1/4-48"-BLACK-12 PCS | TestEquity      | 7000148862                  | 1            | \$19.56              | \$19.56               | [Link](https://www.testequity.com/product/10020784-7000148862)                      

| **Total** | **\$323.76 USD** |




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
