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

Provide detailed information about the inputs, outputs, and data transferred to other subsystems. Ensure specificity and thoroughness, clarifying the method of communication and the nature of the data transmitted.

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

Should there be mechanical elements, display diverse views of the necessary 3D models within the document. Ensure the image's readability and appropriate scaling. Offer explanations as required.
<img width="280" alt="image" src="https://github.com/user-attachments/assets/7b958ffc-730d-46b8-90ab-472bfc7ec6f5" />


## Buildable Schematic 

Integrate a buildable electrical schematic directly into the document. If the diagram is unreadable or improperly scaled, the supervisor will deny approval. Divide the diagram into sections if the text and components seem too small.

The schematic should be relevant to the design and provide ample details necessary for constructing the model. It must be comprehensive so that someone, with no prior knowledge of the design, can easily understand it. Each related component's value and measurement should be clearly mentioned.


## Printed Circuit Board Layout

Include a manufacturable printed circuit board layout.


## Flowchart

For sections including a software component, produce a chart that demonstrates the decision-making process of the microcontroller. It should provide an overview of the device's function without exhaustive detail.


## BOM

Provide a comprehensive list of all necessary components along with their prices and the total cost of the subsystem. This information should be presented in a tabular format, complete with the manufacturer, part number, distributor, distributor part number, quantity, price, and purchasing website URL. If the component is included in your schematic diagram, ensure inclusion of the component name on the BOM (i.e R1, C45, U4).

## Analysis

Deliver a full and relevant analysis of the design demonstrating that it should meet the constraints and accomplish the intended function. This analysis should be comprehensive and well articulated for persuasiveness.

## References

All sources that have contributed to the detailed design and are not considered common knowledge should be duly cited, incorporating multiple references.
