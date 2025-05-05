# Formula SAE Electric Vehicle: Battery Management System

M. Miranda<br/>
Electrical and Computer Engineering Department <br/>
Tennessee Technological University <br/>
mmirandam42@tntech.edu<br/>

## Function of the Subsystem

The Battery Management System (BMS), also referred to as the Accumulator Management System (AMS), functions as an intermediary between the accumulator and the rest of the vehicle’s electrical system. It serves as the supervisory component responsible for monitoring the accumulator’s key parameters, including cell voltage, temperature, and overall system integrity. It continuously verifies that all monitored values remain within the safe operating limits defined by SAE regulations. If a fault is detected—such as an overvoltage condition or a temperature anomaly—the BMS is responsible for initiating safety response. This subsystem is essential not only for intra-system communication and regulatory compliance, but also for protecting the vehicle, its occupants, and surrounding infrastructure.


## Specifications and Constraints

### Specifications

The Battery Management System shall continuously monitor the voltage, temperature, and overall status of the accumulator to ensure safe and reliable operation under all vehicle conditions. It shall function during both charging and active operation of the Tractive System.

The BMS shall promptly detect faults such as out-of-range voltage or temperature, loss of sensor signals, or internal malfunctions. In the event of a fault, the BMS shall trigger shutdown protocol by disabling the vehicle’s high-voltage circuit and activating a red “BMS” indicator light, clearly visible to the seated driver, in compliance with SAE regulations.

The design aims to meet all relevant SAE constraints while ensuring system performance supports consistent speeds up to 55 mph (80.4 kph) in runs of up to 13.6 miles (22 km). These objectives are to be achieved upholding high safety and reliability standards throughout operation.

### Constraints

Per SAE regulations:

   #### Battery Management System - BMS EV.7.3 [1]

   - The Battery Management System shall prevent the maximum current drawn from accumulator T.9.2.2 [1]
   - The Battery Management System shall monitor the Accumulator(s) Voltage EV.7.4 and Temperature EV.7.5 when the EV.7.3.1:  [1]

      - Tractive System is Active EV.11.5  [1]

      - Accumulator is connected to a Charger EV.8.3  [1]

   - The BMS shall have galvanic isolation at each segment to segment boundary, as approved in the ESF EV.7.3.2 [1]

   - Cell balancing is not permitted when the Shutdown Circuit is Open ( EV.7.2, EV.8.4 )  EV.7.3.3 [1]
   
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
 
#### Accumulator Voltage EV.7.4  [1]

- The BMS shall measure the cell voltage of each cell When single cells are directly connected in parallel, only one voltage measurement is needed EV.7.4.1 [1]

- Cell Voltage levels shall stay inside the allowed minimum and maximum cell voltage levels stated in the cell data sheet. Measurement accuracy shall be considered. EV.7.4.2 [1]
- All voltage sense wires to the BMS shall meet one of EV.7.4.3:  [1]

   - Have Overcurrent Protection EV.7.4.4 below  [1]

   - Meet requirements for no Overcurrent Protection listed in EV.7.4.5 below  [1]

- When used, Overcurrent Protection for the BMS voltage sense wires shall meet the two EV.7.4.4:  [1]

  - The Overcurrent Protection shall occur in the conductor, wire or PCB trace which is directly connected to the cell tab.  [1]

   - The voltage rating of the Overcurrent Protection shall be equal to or higher than the maximum segment voltage  [1]

- Overcurrent Protection is not required on a voltage sense wire if all three conditions are met EV.7.4.5:  [1]

   - BMS is a distributed BMS system (one cell measurement per board) [1]

   - Sense wire length is less than 25 mm  [1]

   - BMS board has Overcurrent Protection [1]

#### Accumulator Temperature EV.7.5 [1]

- The BMS shall measure the temperatures of critical points of the Accumulator EV.7.5.1 [1]

- Temperatures (considering measurement accuracy) shall stay below the lower of the two EV.7.5.2:  [1]

     - The maximum cell temperature limit stated in the cell data sheet  [1]

     - 60°C [1]

- Cell temperatures shall be measured at the negative terminal of the respective cell EV.7.5.3 [1]

- The temperature sensor used shall be in direct contact with one of EV.7.5.4:  [1]

     - The negative terminal itself  [1]

     - The negative terminal busbar less than 10 mm away from the spot weld or clamping source on the negative cell terminal [1]

- For lithium based cells, EV.7.5.5:  [1]

   - The temperature of a minimum of 20% of the cells shall be monitored by the BMS  [1]

   - The monitored cells shall be equally distributed inside the Accumulator Container(s) The temperature of each cell should be monitored [1] 

- Multiple cells may be monitored with one temperature sensor, if EV.7.5 is met for all cells sensed by the sensor. EV.7.5.6 [1]


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

Provide a comprehensive list of all necessary components along with their prices and the total cost of the subsystem. 
If the component is included in your schematic diagram, ensure inclusion of the component name on the BOM (i.e R1, C45, U4).

| Item | Manufacturer | Part Number | Distributor | Distributor Part Number | Quantity | Price (USD) | Purchasing Website URL | 
|  :---:   |  :---:  |  :---:   |  :---:   |  :---:   |  :---:   |  :---:   |  :---:   |
|  TinyBMSv2.1 |  ENEPAQ |  TinyBMSv2.1-150A 4s-16s 12V-60V |  DigiKey |  5124-TinyBMSv2.1-150A4s-16s12V-60V-ND |  2 |  389.00 |  [site](https://www.digikey.com/en/products/detail/enepaq/TinyBMSv2-1-150A-4s-16s-12V-60V/21283300) |
|  Total* $  |  |  | |  |  | 778.00 | |

*Shipping not included

## Analysis of Design Decisions:

Deliver a full and relevant analysis of the design demonstrating that it should meet the constraints and accomplish the intended function. This analysis should be comprehensive and well articulated for persuasiveness.

## References

[1] 2025 Formula SAE Rules V.1 [Regulations Manual](https://www.fsaeonline.com/cdsweb/app/NewsItem.aspx?NewsItemID=379e4a8a-80a2-4a74-87c2-6f2de4212270) (Accessed 5/5/2025)

[2] Li-ion building block with Molicel P42A [Datasheet](https://enepaq.com/wp-content/uploads/2025/02/Molicel-P42A-21700-Li-ion-Battery-Module-With-Temperature-Sensor-Datasheet-.pdf)

[3] Tiny BMS s516 – 30A / 150A / 750A [User Manual](https://enepaq.com/wp-content/uploads/2025/02/USER-MANUAL-%E2%80%93-Battery-Management-System-BMS-for-Tiny-BMS-Enepaq-.pdf)

[4] Tiny BMS s516 – 30A / 150A / 750A [Datasheet](https://enepaq.com/wp-content/uploads/2025/02/DATASHEET-%E2%80%93-Battery-Management-System-BMS-for-Tiny-BMS-Enepaq-.pdf)
