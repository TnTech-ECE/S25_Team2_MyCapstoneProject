<h1>Conceptual Design: Battery Management System  

Formula SAE Electric Car Team</h1> 

<h3>Team 2: Maddox Cagle, Dylan Caten, Jordan Davis, Marisol Miranda, Mackenzie Raleigh </h3>

 

 

 

<h2>Introduction:  </h2>

The development of a custom Battery Management System (BMS) for the Formula SAE Electric Car is a crucial step toward ensuring optimal battery performance, safety, and longevity. The primary goal of this project is to create a BMS that monitors battery state, prevents hazardous failures, complies with Formula SAE safety regulations and passes the tests necessary. This document outlines the conceptional design, including the original problem formulation, solution decompositions, specifications, constraints, and an implementation roadmap for the custom BMS.  

 

<h2>Restating the Fully Formulated Problem:  </h2>

A well-designed BMS is essential for preventing battery fire in environments. The system must regulate charge levels, monitor temperature, provide cell balancing, and shut down under unsafe conditions. The formulated problem includes the following “shall” statements: 

* The BMS shall monitor the battery’s state of charge and state of health in real-time. 

* The system shall prevent overcharging, excessive discharge, and overheating. 

* The BMS shall include an automatic shutdown mechanism to reduce safety risks under the following conditions, 
  temperatures bellow -4 degrees Fahrenheit, temperatures at or above 140 degrees Fahrenheit, low charge, excessive 
  discharging, and when overcharging. 

* The system shall integrate with the car’s existing electrical architecture and Formula SAE regulations as listed in the specifications of atomic subsystems. 

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
<h3> Battery(Accumulator)</h3>

<h4> Battery Segments</h4>
The mass of a given segment may not exceed 12 kg. [2]
Each segment must use maintenance plugs to connect to other segments of the battery. [2]
Each segment must be electrically and physically issolated from eachother. [2]
The isolation relay must be used and a minimum of one fuse, to seperate the two poles of the accumulator.[2]
<h5> Battery Cells </h5>
In order to obtain similar electrical charectoristics to the Zero Motor's battery we will need to use lithium ion cells in the battery. Zero motors uses a lithium nickel manganese cobalt (LiNiMnCoO2) which is produced by Farasis.[1] Lithium cobalt has a higher energy density at the cost of battery life and reusability but is not available for commercial purchase.[1]

<h6> Comparison of Cells:</h6>
--Cylindrical lithium ion batteries.
Samsung cells: From the Samsung supplier there are a variety of battery options: [4]
*Molicel model number INR-21700-P45B
-cycle life: reaches 80% power output at 300 cycles
-nominal capacity: 4500 mAh
-approximate weight:  70 g
-country of origin: Tiawan
-nominal voltage: 3.6 V
-maximum voltage: 4.2 V
-price per unit: $7.99
-diameter: 21.55 mm
-length: 70.15 mm
-series connections: 28
-parallel connections: 50
-total units required: 1,400
-total cost of cells: $11,186
-total weight: 216 pounds

*Samsung SDI model number 40T (INR21700-40T)
-cycle life: ~ 250
-nominal capacity: 4000 mAh
-approximate weight:  66.8 g
-country of origin: unlisted
-nominal voltage: 3.6 V
-maximum voltage: 4.2 V
-price per unit: $7.99
-diameter: 21.1 mm
-length: 70.4 mm
-series connections: 28
-parallel connections: 56
-total units required: 1568
-total cost of cells: $12,528.32
-total weight: 232 pounds

*Samsung SDI model number 50T (INR21700-40T)
-cycle life: ~ 250 to 60% capacity
-nominal capacity: 5000 mAh
-approximate weight:  70 g
-country of origin: unlisted
-nominal voltage: 3.6 V
-maximum voltage: 4.2 V
-price per unit: $8.99
-diameter: 21.1 mm
-length: 70.7 mm
-series connections: 28
-parallel connections: 45
-total units required: 1260
-total cost of cells: $11,327.40
-total weight: 195 pounds

--ultra thin cells:
*GMBPOW model number CP142828 
-cycle life: unlisted. discharges at 2% per year at 30 degrees celcius.
-nominal capacity: 100 mAh
-approximate weight:  1.5 g
-country of origin: China
-nominal voltage: 3 V
-maximum voltage: unlisted
-price per unit: $5.00
-Max. dimensions (mm) 1.6×28.5×29 
-series connections: 34
-parallel connections: 1853
-total units required: 63,002
-total cost of cells: $315,010.00
-total weight: 208 pounds

*Huizhou Markyn New Energy Co., LTD. model number CP203030
-cycle life: unlisted. Has a shelf life of 8 yrs.
-nominal capacity: 230 mAh
-approximate weight:  3 g
-country of origin: China
-nominal voltage: 3 V
-maximum voltage: unlisted
-price per unit: $5.00
-Max. dimensions (mm) 2.1×30.0×30.0 
-series connections: 34
-parallel connections: 806
-total units required: 27,404
-total cost of cells: $137,020.00
-total weight: 181 pounds


<h5>Cell Electrical Characteristics </h5>
This group needs to have a nominal output voltage of 102 V DC to match the output voltage of the Zero Motor's battery. [3] The output voltage is given by the number of cells connected in series and the cell's output voltage. Most cells have a typical output voltage of 3.6 V, so this group will need to connect 28 battery cells in series if one is using the molicel cylindrical battery.

This group needs a nominal energy capacity of 6.3 kWh to match the specifications of the Zero Motor's battery. [3] This is found by multiplying the nominal cell capacity in amp hours (Ah) multiplied by the series and parrallel connections. For the above example this group will need 56.25 parallel connections to achieve the same nominal energy capacity.

<h5> Sensors</h5>
Inside the battery this group is required to have a voltage indicator which controls the output voltage. This group is also required to have temperature sensors and voltage sensors to monitor the cell voltage and temperature for the battery management system.[2] The voltage indicator must be controlled by the shutdown circuit.
Because energy efficency is important, this group must use a lithium ion battery, which by the rules requires at least 40% of  the battery cells to be monitored by temperature.

<h3> Battery Management System (BMS)</h3> 
The battery management system must monitor the voltage and temperature of the cells when the battery is charging or when the vehicle is running. [2]
The temperature must be measured at the negative terminal of the battery cells. [2] 
If any battery cell exceed 60 degrees celcius, the battery management system must trigger the voltage indicator to stop providing voltage. [2]
If the above condition is met, then the BMS must send a signal that triggers the BMS warning light.[2]

<h4> Discharge Circuit</h4>
A circuit that is always active when the shutdown circuit is open.[2] Cannot use positive temperature coefficent devices to limit the current.[2]
This group also wants to impliment a current limiting behavior in the BMS when the accumulator approaches the shutoff temperature to prevent reaching the shuttoff temperature and reduce the risk of fire.
<h4> Precharge Circuit</h4>
The precharge circuit must be able to charge the accumulator up to 90% of its capacity before closing the isolation relay.[2] It must be mechanical in design. [2] Cannot use positive temperature coefficent devices to limit the current.[2]

While this team could solve the battery management system of the Zero Motor’s 2022 battery, this project is already being developed by the current ECE capstone team. As such, this is not an option for this group. 

<h2>High-Level Solution</h2>

This team will design a battery using a molicel battery cell model number INR-21700-P45B which requires 28 series connections and 50 parralel connections to achieve the same electrical characteristics as the Zero Motor's battery with a weight of the battery cells alone at  98 kg or 216 pounds
 

This team shall design a battery that has similar electrical and volume characteristics to the 2022 Zero Motor’s motorcycle battery with a knowable battery management system to be used as a backup for the Formula SAE event. 

<h2>Hardware Block Diagram </h2>

![Capture](https://github.com/user-attachments/assets/2736f964-2aea-439d-9cae-8d7a974ce6d6)



<h2>Operational Flow Chart </h2>


![Capstone_I_ConceptualDesign_Flowchart1](https://github.com/user-attachments/assets/f7fd3949-ff1b-418a-b5cb-52538a6ff7fd)


<h2>Atomic Subsystem Specifications: </h2>

<ins> Battery Pack </ins>

* The battery pack shall store and supply energy to the car’s motor and electronics.

* It shall convert chemical energy into electrical energy and provide high-power discharge to meet performance 
  requirements.
  
* The battery pack shall interface with the BMS for protection and monitoring. 

* The battery pack shall provide DC power to the Electronic Speed Controller and Auxiliary Electronics.

* The battery pack shall send an analog voltage signal to the Battery Management System for monitoring. 

* The battery pack shall receive DC power from the charging circuit during charging.
 
<ins> Battery Management System </ins>

* The BMS shall protect and manage the battery pack to ensure safety and efficiency.
  
* It shall monitor individual cell voltage, temperature, and current, balance cell voltages during charging, and prevent 
  overcharge, over-discharge, short-circuit, and overheating.
  
* The BMS shall communicate battery status to the vehicle control system. 

* The BMS shall receive analog signals (cell voltages, temperature) from the Battery Pack.

* The BMS shall send power control signals (MOSFET switching) to the Battery Output.

* The BMS shall send serial data (I2C, CAN, or UART) to the Vehicle Control Unit for telemetry.

* The BMS shall receive power from the charging circuit.

<ins> Charging Circuit </ins>

* The Charging Circuit shall provide regulated DC voltage and current to the battery pack while ensuring safe operation 
  through BMS control. 

* The charger shall output DC power to the Battery Pack. 

* The charger shall send serial data to the BMS. 

* The charger shall receive AC power from an External Power Source. 

* The charger shall communicate charge status, voltage, and current to the BMS using CAN Bus or UART. 

<h2>Ethical, Professional, and Standards Considerations: </h2>

The design of the BMS and battery must account for its broader impact on culture, society, the environment, public health, public safety, and the economy. Several key considerations influence the design process: 

Public Safety and Compliance: The BMS must meet Formula SAE safety standards and industry best practices to prevent overheating, fires, and electrical failures that could endanger users and surrounding individuals. 

Environmental Responsibility: Lithium-ion batteries pose recycling and disposal challenges. The design process must incorporate sustainability measures, including adherence to regulations for battery disposal and potential integration of battery recycling programs. 

Economic and Society Impact: The BMS contributes to advancing electric vehicle technology, supporting the transition to sustainable transportation. The affordability and efficiency of the system impact both student engineering teams and potential real-world applications. 

Engineering Standards: The project follows Institute of Electrical and Electronics Engineers (IEEE), SAE, and other relevant technical standards to ensure best practices in system design, power management, and safety features. Adherence to these standards ensures interoperability and reliability. 

Ethical Considerations: The team is committed to responsible sourcing of materials, ensuring that no components come from unethical labor practices. Transparency in design and testing is a key priority to maintain the integrity of the engineering profession. 

<h2>Resources </h2>

<h3>Budget </h3>

|Item/Material | Quantity | Cost(USD) | 
|--------------|----------|-----------|
|Lithium Battery Total|361|>~$2,176|
|Battery Case/Insulation|~1|~$100|
|Contactor|1|~$100|
|Temperature Sensor|1|$188|
|Voltage Sensor|1|$133|
|Current Sensor|1|$40|
|Fuse|1|$45|
|BMS Components| 1 | >~$1,000| 
|Wire and Connectors| <1 |~$500|
|Total| |~$4,282|

<h2>Division of Labor </h2>

|Team Member |Subsystem | 
|--------------|----------|
| Maddox | Discharge Circuit, BMS |
| Dylan | Sensors, Battery Pack |
| Jordan | Charging Circuit |
| Marisol | BMS |
| Mackenzie | Structure and Alignment, Battery Pack |


 

<h2>Timeline </h2>

Revise the detailed timeline (Gantt chart) you created in the project proposal. Ensure that the timeline is optimized for detailed design. Address critical unknowns early and determine if a prototype needs to be constructed before the final build to validate a subsystem. Additionally, if subsystem A imposes constraints on subsystem B, generally, subsystem A should be designed first. 

 

<h2>References </h2>


[1] Unofficial Zero Manual. "Battery/Cells".zeromanual.https://zeromanual.com/wiki/Battery/Cells (accessed March 14, 2025). 

[2] Formula SAE Rules 2025, Formula SAE, 2025.

[3] "Zero Motors Cypher 2 Powertrain Datasheet," Source.[Online] Available: https://zero-cms-disco.cdn.prismic.io/zero-cms-disco/372e4e04-53f3-4f30-9bf2-7e3e5fc1a901_powertrain-data-sheet.pdf
[4] IMR batteries.com.https://imrbatteries.com/collections/21700-batteries (Accessed 3/28/2025) 
 

<h2>Statement of Contributions </h2>

Maddox: budget, operation flow chart

Dylan: comparison of solutions, hardware block diagram, operation flow chart

Jordan: atomic subsystem specifications

Marisol: hardware block diagram, personnel, timeline

Mackenzie: intro, restating the problem, ethics 

