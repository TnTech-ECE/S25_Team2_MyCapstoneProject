# Formula SAE Electric Vehicle: Battery Management System
```
M. Miranda
Tennessee Technological University 
ECE Department 
mmirandam42@tntech.edu
```
## Function of the Subsystem

This segment should elucidate the role of the subsystem within the entire system, detailing its intended function, aligned with the conceptual design.


## Specifications and Constraints

### Specifications

   #### Battery Management System - BMS EV.7.3 [1]

   - Prevents the maximum current draw from accumulator T.9.2.2 [1]

   2. A Battery Management System shall monitor the Accumulator(s) Voltage EV.7.4 and Temperature EV.7.5 when the EV.7.3.1:  [1]

   - Tractive System is Active EV.11.5  [1]

   - Accumulator is connected to a Charger EV.8.3  [1]

   3. The BMS shall have galvanic isolation at each segment to segment boundary, as approved in the ESF EV.7.3.2 [1]

   - The BMS shall monitor for EV.7.3.4: [1]

   - Voltage values outside the allowable range EV.7.4.2 [1]

   - Voltage sense Overcurrent Protection device(s) blown or tripped [1]

      - Temperature values outside the allowable range EV.7.5.2 [1]

      - Missing or interrupted voltage or temperature measurements [1]

      - A fault in the BMS [1]

   - If the BMS detects one or more of the conditions of EV.7.3.4 above, the BMS shall EV.7.3.5 : [1]

      - Open the Shutdown Circuit EV.7.2.2 [1]

      - Turn on the BMS Indicator Light and the Tractive System Status Indicator EV.5.11.5 The two lights shall stay on 
        until the BMS is manually reset EV.7.2.3 [1]

   - The BMS Indicator Light shall be EV.7.3.6: [1]

      - Color: Red [1]

      - Clearly visible to the seated driver in bright sunlight [1]

      - Clearly marked with the lettering “BMS” [1]


### Constraints


## Overview of Proposed Solution

Describe the solution and how it will fulfill the specifications and constraints of this subsystem.


## Interface with Other Subsystems

Provide detailed information about the inputs, outputs, and data transferred to other subsystems. Ensure specificity and thoroughness, clarifying the method of communication and the nature of the data transmitted.


## 3D Model of Custom Mechanical Components

Should there be mechanical elements, display diverse views of the necessary 3D models within the document. Ensure the image's readability and appropriate scaling. Offer explanations as required.


## Buildable Schematic 

Integrate a buildable electrical schematic directly into the document. If the diagram is unreadable or improperly scaled, the supervisor will deny approval. Divide the diagram into sections if the text and components seem too small.

The schematic should be relevant to the design and provide ample details necessary for constructing the model. It must be comprehensive so that someone, with no prior knowledge of the design, can easily understand it. Each related component's value and measurement should be clearly mentioned.


## Printed Circuit Board Layout

Include a manufacturable printed circuit board layout.


## Flowchart

For sections including a software component, produce a chart that demonstrates the decision-making process of the microcontroller. It should provide an overview of the device's function without exhaustive detail.


## BOM

Provide a comprehensive list of all necessary components along with their prices and the total cost of the subsystem. This information should be presented in a tabular format, complete with the manufacturer, part number, distributor, distributor part number, quantity, price, and purchasing website URL. If the component is included in your schematic diagram, ensure inclusion of the component name on the BOM (i.e R1, C45, U4).

## Analysis of Design Decisions:

Deliver a full and relevant analysis of the design demonstrating that it should meet the constraints and accomplish the intended function. This analysis should be comprehensive and well articulated for persuasiveness.

## References

[1] Formula SAE Rules 2025, Formula SAE, 2025. https://www.fsaeonline.com/cdsweb/app/NewsItem.aspx?NewsItemID=379e4a8a-80a2-4a74-87c2-6f2de4212270 (Accessed 5/5/2025)

[2] Li-ion building block with Molicel P42A datasheet. https://enepaq.com/wp-content/uploads/2025/02/USER-MANUAL-%E2%80%93-Battery-Management-System-BMS-for-Tiny-BMS-Enepaq-.pdf

[3] Tiny BMS s516 – 30A / 150A / 750A User Manual. https://enepaq.com/wp-content/uploads/2025/02/Molicel-P42A-21700-Li-ion-Battery-Module-With-Temperature-Sensor-Datasheet-.pdf

[4] Tiny BMS s516 – 30A / 150A / 750A Datasheet. https://enepaq.com/wp-content/uploads/2025/02/DATASHEET-%E2%80%93-Battery-Management-System-BMS-for-Tiny-BMS-Enepaq-.pdf
