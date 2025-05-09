# <div align="center"> Detailed Design: Precharge Circuit
### <div align="center"> Precharge Circuit
#### <div align="center"> Jordan M. Davis
<div align="center"> Capstone Team 2
<div align="left">
   
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

   - The main contactor shall close only after the precharge voltage condition has been met.

   - The precharge resistor shall be rated for a minimum of 225 W continuous and sufficient pulse energy to handle full 
     charge-up events.

   - The system shall open the precharge relay immediately after the main contactor is closed to prevent overheating of 
     the resistor.
      
   ### Constraints

#### The Precharge Circuit shall: [5]

   - Be able to charge the Intermediate Circuit to minimum 90% of the Accumulator voltage before closing the second IR 
     [5]
   
   - Be supplied from the Shutdown Circuit EV.7.1 [5]
   
   - The Accumulator shall contain a Precharge Circuit. EV.5.6.1 [5]

   - Positive Temperature Coefficient (PTC) devices shall not be used to limit current for the Precharge Circuit 
     EV.5.6.4 [5]

   - The precharge relay shall be a mechanical type relay EV.5.6.5 [5]


## Overview of Proposed Solution

This precharge circuit is designed to safely energize the high-voltage system in a Formula SAE Electric vehicle using an Orion BMS 2 and a modular lithium-ion battery pack. Its primary function is to protect components like the motor controller from harmful inrush currents when the system is first powered on.

The circuit includes a 100 Ω, 225 W Ohmite resistor to limit inrush current, controlled by a TE EV200AAANA relay during the precharge phase. Once the system voltage stabilizes—based on timing or internal BMS logic—a Gigavac GV200MDA main contactor closes to deliver full power and bypass the resistor.

The Orion BMS 2 directly controls both the precharge relay and the main contactor using its digital outputs. It also monitors pack voltage and fault conditions, ensuring precharge occurs only under safe operating parameters.

This configuration simplifies integration, maintains full compliance with FSAE Electric rules, and provides a reliable solution for safely managing high-voltage startup in an electric race car.


## Interface with Other Subsystems

### Precharge Relay Control (K1)

 - Controlled by Orion BMS 2 Pin 23 (Multipurpose Output).

 - The BMS energizes this output to close the precharge relay when precharge conditions are safe (e.g., no fault).

### Main Contactor Control (K2)

 - Controlled by Orion BMS 2 Pin 7 (Discharge Enable Output).
   
 - The BMS automatically enables the main contactor once it detects that the voltage across the load (motor controller) is 
   close to pack voltage.

### Voltage Sensing For Precharge Completion

 - The BMS uses time-based logic or feedback from a digital input (Pin 8) to determine when precharge is complete.
   
## 3D Model of Custom Mechanical Components

<img width="600" alt="3D_Drawing" src="https://github.com/user-attachments/assets/7b958ffc-730d-46b8-90ab-472bfc7ec6f5" />

This image shows the key components of a precharge circuit used in electric vehicles, such as Formula SAE cars. The large green resistor (Ohmite L225J100E) is approximately 50 mm long, 15 mm tall, and 10 mm wide, and is used to limit inrush current during system startup. The high-voltage contactors, each roughly 70 mm × 50 mm × 40 mm, control when power is routed through the resistor or directly from the battery. The bottom-right view provides a simple wiring layout, illustrating how the resistor and contactors connect to safely manage voltage buildup before the main contactor closes. This diagram helps visualize how components will be mounted and wired within the enclosure.

## Buildable Schematic 

<img width="382" alt="image" src="https://github.com/user-attachments/assets/a1408598-6ad1-4bdf-a3da-90fcad5a41ce" />

This schematic illustrates a precharge circuit for a high-voltage EV system, designed to safely charge the motor controller's input capacitors before the main contactor (K2) closes. At power-up, the high-voltage supply passes through a precharge resistor (R1) and a precharge relay (K1), limiting the inrush current to the motor controller. The Orion BMS 2 directly controls both K1 and K2. Once internal logic or system voltage indicates that precharge is complete, the BMS deactivates K1 and activates K2, closing the full-current path and bypassing the resistor. 

## Printed Circuit Board Layout

![image](https://github.com/user-attachments/assets/428563cf-ddcb-4375-b4c5-4861bab4e8eb)

This PCB layout represents the control board for a precharge circuit in an electric vehicle system. The board includes labeled footprints for the main components: a 100 Ω precharge resistor (R1), and two relays—K1 for precharge and K2 for the main contactor. Control signals for both relays are routed directly to and from the Orion BMS 2, which manages the switching logic.

## Flowchart

![image](https://github.com/user-attachments/assets/f9127d88-69c0-43b0-bbfe-ee305400b1ef)

This flowchart outlines the logic used to manage the precharge process in a high-voltage electric vehicle. The process begins with closing the precharge relay to allow current to flow through a resistor, gradually charging the motor controller’s input capacitors. The BMS monitors the motor controller voltage (V_mc) and compares it to 90% of the battery pack voltage (V_pack). If the condition is met within 3 seconds, the main contactor is closed and the precharge relay is opened. If the voltage threshold is not reached in time, the system registers a fault and disables further action to protect the hardware.

## BOM

| Item | Component                | Manufacturer    | Part Number       | Distributor     | Distributor Part # | Qty | Unit Price (USD) | Total (USD) | Purchase URL                                                                         |
| ---- | ------------------------ | --------------- | ----------------- | --------------- | ------------------ | --- | ---------------- | ----------- | ------------------------------------------------------------------------------------ |
| R1    | Precharge Resistor       | Ohmite          | L225J100E         | Digi-Key        | 273-L225J100E-ND   | 1   | \$37.20          | \$37.20     | [Link](https://www.digikey.com/en/products/detail/ohmite/L225J100E/823557)           |
| K1    | Precharge Relay          | TE Connectivity | EV200AAANA        | Mouser          | 655-EV200AAANA     | 1   | \$80.00          | \$80.00     | [Link](https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA)      |
| K2    | Main Contactor           | Gigavac         | GV200MA-1         | Mouser          | 682-GV200MA-1      | 1   | \$145.00         | \$145.00    | [Link](https://www.mouser.com/ProductDetail/GIGAVAC/GV200MA-1)                       |
| W1    | Precharge Harness Wire   | Southwire       | TXL22-4           | IEWC            | TXL22-4            | 20  | \$0.10/ft        | \$2.00      | [Link](https://www.iewc.com/product/txl22-4)                                         |
| J1    | Relay Connector Housing  | TE Connectivity | 776523-3          | TE Connectivity | 776523-3           | 1   | \$1.50           | \$1.50      | [Link](https://www.te.com/en/product-776523-3.html)                                  |
|  B1   | Contact Boots/Insulation | HellermannTyton | MS3109-06AU       | PEI-Genesis     | MS3109-06AU        | 2   | \$5.00           | \$10.00     | [Link](https://www.peigenesis.com/en/shop/f/MS3109.html)                             |
| HW1   | Mounting Hardware        | Generic         | M4 x 20mm SS Bolt | Accu Components | SEBF-M4-20-A2      | 5   | \$0.22           | \$1.10      | [Link](https://accu-components.com/us/full-thread-hexagon-bolts/18823-SEBF-M4-20-A2) |
| HS1    | Heatshrink Tubing        | 3M              | EPS-300-1/4-48"   | TestEquity      | 7000148862         | 1   | \$19.56          | \$19.56     | [Link](https://www.testequity.com/product/10020784-7000148862)                       |
                   

| **Total** | **\$296.36 USD** |




## Analysis

The presented precharge circuit design incorporates key components including a 100 Ω, 225 W Ohmite resistor, a TE Connectivity EV200AAANA relay, and a Gigavac GV200 series main contactor, integrated under the control of an Orion BMS 2. This configuration effectively meets the operational, safety, and regulatory constraints required for a Formula SAE Electric vehicle operating at 102 V nominal and 6.3 kWh capacity.

### Functionality and System Behavior

At power-up, motor controllers present a near-short circuit due to their large DC link capacitors. If the main contactor were closed immediately, a damaging inrush current, hundreds of amps—would flow. The precharge resistor solves this by temporarily introducing resistance in the HV path, reducing the initial current spike.

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

3. Orion BMS 2 Integration

   - The Orion BMS 2 supports configurable digital outputs and CAN messaging, both of which can be used to initiate 
     precharge and monitor system status.

   - Its built-in fault detection (cell voltage, temperature, overcurrent) ensures precharge only occurs under safe 
     conditions.

   - CAN integration enables high-resolution monitoring of pack voltage, providing an accurate reference for precharge 
     completion logic.
     
### Thermal and Reliability Considerations

The precharge resistor’s peak energy during a full precharge is: E =(1/2) * C * V^2
Assuming DC link capacitance of 1,000 μF: E = 0.5 * 0.001 * 102^2 = 5.2 J
The Ohmite resistor’s ceramic enclosure and 225 W continuous rating far exceed this transient energy, ensuring long life and tolerance to frequent cycling.

The EV200 relay and GV200 contactor are hermetically sealed and vibration-resistant, designed specifically for electric vehicle applications. Their long cycle life and robust isolation reduce the risk of arc faults or welding under high load conditions.

### Mechanical Fit and Maintainability

As shown in the associated CAD image, the components are compact, bolt-mountable, and easily routed. The image also offers a wiring example that simplifies implementation in an accumulator enclosure or HV distribution box. The modularity of the design enables easy diagnostics, replacement, and expansion (e.g., adding discharge circuitry or auxiliary contact monitoring).

## References

[1] Ohmite Manufacturing Company, 270 Series Wirewound Resistors - L225J100E Datasheet, Ohmite, 2023. [Online]. Available: https://www.ohmite.com/catalog/270-series/L225J100E

[2] TE Connectivity, EV200AAANA DC Contactor – Product Specification Sheet, TE Connectivity Ltd., 2023. [Online]. Available: https://www.te.com/en/product-1618002-7.html

[3] Sensata Technologies, GV200 Series Sealed Power Contactors – Datasheet, Sensata Gigavac, 2023. [Online]. Available: https://www.sensata.com/sites/default/files/a/sensata-gigavac-gv200-series-open-contactors-datasheet.pdf

[4] Ewert Energy Systems, Orion BMS 2 Operational Manual, OrionBMS.com, Revision 3.3, 2023. [Online]. Available: https://www.orionbms.com/manuals/pdf/orionbms2_operational_manual.pdf

[5] Formula SAE Rules 2025, Formula SAE, 2025.
