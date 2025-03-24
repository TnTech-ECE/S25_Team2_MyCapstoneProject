<h1>Conceptual Design: Battery Management System  

Formula SAE Electric Car Team</h1> 

<h3>Team 2: Maddox Cagle, Jordan Davis, Mackenzie Raleigh, Marisol Miranda, Dylan Caten </h3>

 

 

 

<h2>Introduction:  </h2>

The development of a custom Battery Management System (BMS) for the Formula SAE Electric Car is a crucial step toward ensuring optimal battery performance, safety, and longevity. The primary goal of this project is to create a BMS that monitors battery state, prevents hazardous failures, complies with Formula SAE safety regulations and passes the tests necessary. This document outlines the conceptional design, including the original problem formulation, solution decompositions, specifications, constraints, and an implementation roadmap for the custom BMS.  

 

<h2>Restating the Fully Formulated Problem:  </h2>

A well-designed BMS is essential for preventing battery fire in environments. The system must regulate charge levels, monitor temperature, provide cell balancing, and shut down under unsafe conditions. The formulated problem includes the following “shall” statements: 

* The BMS shall monitor the battery’s state of charge and state of health in real-time. 

* The system shall prevent overcharging, excessive discharge, and overheating. 

* The BMS shall include an automatic shutdown mechanism to reduce safety risks under the following conditions, 
  temperatures bellow -4 degrees Fahrenheit, temperatures at or above 140 degrees Fahrenheit, low charge, excessive 
  discharging, and when overcharging. 

* The system shall integrate with the car’s existing electrical architecture and Formula SAE regulations. 

* The total project cost shall not exceed $10,000, ensuring cost-effectiveness. 

<h3>Constraints and Their Origins </h3>

The design of the BMS must adhere to several constraints imposed by competition rules, engineering standards, and fire safety concerns. These include: 

* Safety Regulations: The BMS must comply with Formula SAE safety standards, including fire prevention and automatic 
  shutdown in hazardous conditions as stated above. 

* Material Constraints: The battery must be enclosed in non-flammable housing to meet industry and competition safety 
  guidelines. 

* Economic Feasibility: The total cost must remain under budget to ensure financial viability and to score well in the 
  cooresponding Formula SAE test.  

* Technical Compatibility: The BMS must be compatible with the vehicle’s electrical system which is currently being 
  designed for the Zero Motor's battery, ensuring seamless integration. 

<h2>Comparative Analysis of Potential Solutions </h2>
The formula sae event has many regulations regarding the battery and battery management system and while they do constrain options for they also help guide system design. Additionally, the battery and battery management system under design must mimick the Zero Motor's battery so that it may be used on the current vehicle.
<h3> Battery(accumulator)</h3>

<h4> Battery Segments</h4>
The mass of a given segment may not exceed 12 kg. [2]
Each segment must use maintenance plugs to connect to other segments of the battery. [2]
Each segment must be electrically and physically issolated from eachother. [2]
The isolation relay must be used and a minimum of one fuse, to seperate the two poles of the accumulator.[2]
<h5> Battery Cells </h5>
In order to obtain similar electrical charectoristics to the Zero Motor's battery we will need to use lithium ion cells in the battery. Zero motors uses a lithium nickel manganese cobalt (LiNiMnCoO2) which is produced by Farasis.[1] Lithium cobalt has a higher energy density at the cost of battery life and reusability.[1]

<h5>Cell Electrical Characteristics </h5>
This group needs to have a nominal output voltage of 102 V DC to match the output voltage of the Zero Motor's battery. [3] The output voltage is given by the number of cells connected in series and the cell's output voltage. 

This group needs a nominal energy capacity of 6.3 kWh to match the specifications of the Zero Motor's battery. [3] This is found by multiplying the nominal cell capacity in Ah multiplied by the series and parrallel connections.

<h5> Sensors</h5>
Inside the battery this group is required to have a voltage indicator which controls the output voltage. This group is also required to have temperature sensors and voltage sensors to monitor the cell voltage and temperature for the battery management system.[2] The voltage indicator must be controlled by the shutdown circuit.

<h4> Battery Management System (BMS)</h4> 
The battery management system must monitor the voltage and temperature of the cells when the battery is charging or when the vehicle is running. [2]
The temperature must be measured at the negative terminal of the battery cells. [2] 
If any battery cells exceed 60 degrees celcius, the battery management system must trigger the voltage indicator to stop providing voltage. [2]
If the above condition is met, then the BMS must send a signal that triggers the BMS warning light.[2]

<h5> Discharge Circuit</h5>
A circuit that is always active when the shutdown circuit is open.[2] Cannot use positive temperature coefficent devices to limit the current.[2]
This group also wants to impliment a current limiting behavior in the BMS when the accumulator approaches the shutoff temperature to prevent reaching the shuttoff temperature and reduce the risk of fire.
<h5> Precharge Circuit</h5>
The precharge circuit must be able to charge the accumulator up to 90% of its capacity before closing the isolation relay.[2] It must be mechanical in design. [2] Cannot use positive temperature coefficent devices to limit the current.[2]

While this team could solve the battery management system of the Zero Motor’s 2022 battery, this project is already being developed by the current ECE capstone team. As such, this is not an option for this group. 

A variety of different battery options are available, however, the current vehicle under design is made assuming that the Zero Motor battery will be used in it. This requires the group to get a certain voltage and energy density is a predetermined area.
To compensate for this the group shall use similar materials to the Zero Motor battery. This will allow the group to mimic the electrical characteristics with proper cell placement.
It does mean, however, that this group shall implement its own battery management system that shall be of a similar size to Zero Motor’s battery management system, which will require the design to be optimal in both size and charge per area. 

High-Level Solution

This section presents a comprehensive, high-level solution aimed at efficiently fulfilling all specified requirements and constraints. The solution is designed to maximize stakeholder goal attainment, adhere to established constraints, minimize risks, and optimize resource utilization. Please elaborate on how your design accomplishes these objectives. 

This team must design a battery with the same output charectoristics of the Zero Motor's battery.
Additionally, this group must design the BMS and battery to comply with Formula SAE rules.
 

This team shall design a battery that has similar electrical and volume characteristics to the 2022 Zero Motor’s motorcycle battery with a knowable battery management system to be used as a backup for the Formula SAE event. 

<h2>Hardware Block Diagram </h2>

![Capture](https://github.com/user-attachments/assets/2736f964-2aea-439d-9cae-8d7a974ce6d6)



<h2>Operational Flow Chart </h2>

Similar to a block diagram, the flow chart aims to specify the system, but from the user's point of view rather than illustrating the arrangement of each subsystem. It outlines the steps a user needs to perform to use the device and the screens/interfaces they will encounter. A diagram should be drawn to represent this process. Each step should be represented in the diagram to visually depict the sequence of actions and corresponding screens/interfaces the user will encounter while using the device. 

![Capstone_I_ConceptualDesign_Flowchart1](https://github.com/user-attachments/assets/f7fd3949-ff1b-418a-b5cb-52538a6ff7fd)


<h2>Atomic Subsystem Specifications: </h2>

<ins> Battery Pack </ins>

* The battery pack shall store and supply energy to the car’s motor and electronics.

* It shall convert chemical energy into electrical energy and provide high-power discharge to meet performance 
  requirements.
  
* The battery pack shall interface with the BMS for protection and monitoring. 

* The battery pack shall provide DC power to the Electronic Speed Controller and Auxiliary Electronics.

* The battery pack shall send an analog voltage signal to the Battery Management System for monitoring. 

* The battery pack shall receive DC power from the Battery Charger during charging.
 
<ins> Battery Management System </ins>

* The BMS shall protect and manage the battery pack to ensure safety and efficiency.
  
* It shall monitor individual cell voltage, temperature, and current, balance cell voltages during charging, and prevent 
  overcharge, over-discharge, short-circuit, and overheating.
  
* The BMS shall communicate battery status to the vehicle control system. 

* The BMS shall receive analog signals (cell voltages, temperature) from the Battery Pack.

* The BMS shall send power control signals (MOSFET switching) to the Battery Output.

* The BMS shall send serial data (I2C, CAN, or UART) to the Vehicle Control Unit for telemetry.

* The BMS shall receive power from the Battery Charger.

<ins> Power Distribution System </ins>

* The Power Distribution Unit shall distribute power efficiently to all components, regulating power to different subsystems such as the motor, electronics, and sensors.
  
* The PDU shall contain fuses and relays for power safety. 

* The PDU shall receive DC power from the Battery Pack.

* The PDU shall distribute power to the ESC, Auxiliary Electronics, and Sensors.

* The PDU shall send an analog signal (current sensor data) to the VCU.

* The PDU shall report power distribution status to the VCU using the CAN Bus communication protocol.

<ins> Electronic Speed Controller </ins>

* The ESC shall regulate motor speed and torque based on throttle input.

* It shall convert DC power into controlled three-phase AC power for the motor and provide regenerative braking support. 

* The ESC shall receive a PWM signal (throttle control) from the VCU.

* The ESC shall receive DC power from the PDU/Battery Pack.

* The ESC shall output three-phase AC power to the Electric Motor.

* The ESC shall send serial data (ESC telemetry) to the VCU using CAN Bus or UART.

<ins> Vehicle Control Unit </ins>

* The VCU shall serve as the central processing unit that manages power, motor control, and user commands.

* It shall read sensor data and battery status while controlling throttle, braking, and power management. 

* The VCU shall receive serial data (I2C, CAN) from the BMS, PDU, and ESC.

* The VCU shall receive analog signals from throttle and brake sensors.

* The VCU shall send PWM control signals to the ESC. 

* The VCU shall send telemetry data to the User Interface Display. 

* The VCU shall communicate with the BMS, PDU, and ESC using CAN Bus. 

* The VCU shall optionally send telemetry data to a mobile app or remote monitoring system using Bluetooth/WiFi.

<ins> Charging System </ins>

* The Charging System shall provide regulated DC voltage and current to the battery pack while ensuring safe operation 
  through BMS control. 

* The charger shall output DC power to the Battery Pack. 

* The charger shall send serial data to the BMS. 

* The charger shall receive AC power from an External Power Source. 

* The charger shall communicate charge status, voltage, and current to the BMS using CAN Bus or UART. 

<h2>Ethical, Professional, and Standards Considerations: </h2>

The design of the BMS must account for its broader impact on culture, society, the environment, public health, public safety, and the economy. Several key considerations influence the design process: 

Public Safety and Compliance: The BMS must meet Formula SAE safety standards and industry best practices to prevent overheating, fires, and electrical failures that could endanger users and surrounding individuals. 

Environmental Responsibility: Lithium-ion batteries pose recycling and disposal challenges. The design process must incorporate sustainability measures, including adherence to regulations for battery disposal and potential integration of battery recycling programs. 

Economic and Society Impact: The BMS contributes to advancing electric vehicle technology, supporting the transition to sustainable transportation. The affordability and efficiency of the system impact both student engineering teams and potential real-world applications. 

Engineering Standards: The project follows Institute of Electrical and Electronics Engineers (IEEE), SAE, and other relevant technical standards to ensure best practices in system design, power management, and safety features. Adherence to these standards ensures interoperability and reliability. 

Ethical Considerations: The team is committed to responsible sourcing of materials, ensuring that no components come from unethical labor practices. Transparency in design and testing is a key priority to maintain the integrity of the engineering profession. 

<h2>Resources: Maddox and Marisol </h2>

You have already estimated the resources needed to complete the solution. Now, let's refine those estimates. 

 

<h2>Budget </h2>

Develop a budget proposal with justifications for expenses associated with each subsystem. Note that the total of this budget proposal can also serve as a specification for each subsystem. After creating the budgets for individual subsystems, merge them to create a comprehensive budget for the entire solution. 

 |Item/Material | Quantity | Cost(USD) | 
|--------------|----------|-----------|
|Battery Construction Components| <1 | >~$7,050 |
|BMS Components| 1 | >~$1,000| 
|Wire and Connectors| <1 |~$500|
|Total| |~$8,550|

<h2>Division of Labor </h2>

First, conduct a thorough analysis of the skills currently available within the team, and then compare these skills to the specific requirements of each subsystem. Based on this analysis, appoint a team member to take the specifications for each subsystem and generate a corresponding solution (i.e. detailed design). If there are more team members than subsystems, consider further subdividing the solutions into smaller tasks or components, thereby allowing each team member the opportunity to design a subsystem. 

 

<h2>Timeline </h2>

Revise the detailed timeline (Gantt chart) you created in the project proposal. Ensure that the timeline is optimized for detailed design. Address critical unknowns early and determine if a prototype needs to be constructed before the final build to validate a subsystem. Additionally, if subsystem A imposes constraints on subsystem B, generally, subsystem A should be designed first. 

 

<h2>References </h2>

All sources utilized in the conceptual design that are not considered common knowledge must be properly cited. Multiple references should be included. 
[1] Unofficial Zero Manual. "Battery/Cells".zeromanual.https://zeromanual.com/wiki/Battery/Cells (accessed March 14, 2025). 

[2] Formula SAE Rules 2025, Formula SAE, 2025.

[3] "Zero Motors Cypher 2 Powertrain Datasheet," Source.[Online] Available: https://zero-cms-disco.cdn.prismic.io/zero-cms-disco/372e4e04-53f3-4f30-9bf2-7e3e5fc1a901_powertrain-data-sheet.pdf
 

<h2>Statement of Contributions </h2>

Each team member is required to make a meaningful contribution to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate. 

