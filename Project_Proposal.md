<h1> Formula SAE Electric Car </h1> 

<h2> Project Proposal </h2>

 Maddox Cagle, Dylan Caten, Jordan Davis, Marisol Miranda, Mackenzie Raleigh 

 

<h3>Introduction: </h3> 

This proposal outlines the design and implementation of a new Battery Management System (BMS) for a Formula SAE Electric Car. The BMS shall be a critical component for ensuring performance, safety, and longevity in electric vehicles, particularly in a competitive racing environment. An optimally designed BMS shall manage the state of charge, state of health, temperature control, and cell balancing of the battery pack. This system will significantly enhance the efficiency and safety of the electric car, rendering it a viable contender in the Formula SAE race in the upcoming year. This report shall present the design methodology, specifications, success criteria, resources required, and project schedule. In addition, it will also examine ethical and social concerns involving the design and deployment of the BMS and its impact on the broader customer- Tennessee Technological University’s Electrical and Computer Engineering (ECE) Department.  

<h3>Problem Formulation: </h3> 

The Formula SAE Electric Competition requires teams to design and build an electric race car that meets high standards of performance, endurance, and safety specifications. A critical component of this system is the battery pack, which must supply energy for high-speed operation while maintaining durability throughout the competition. Safety shall be paramount to protect the driver, team, and university facilities from risks such as overheating, short circuits, battery failure, or electric fires.  

Off-the-shelf batteries solutions are either too expensive, too heavy, or lack the necessary power and longevity for a competitive race. Given these limitations, the SAE team and ECE Department shall design a custom battery system that sustains the power output required for racing while remaining lightweight to improve vehicle efficiency and handling. The battery shall also be cost-effective compared to pre-assembled alternatives and shall incorporate a reliable BMS to monitor performance and prevent hazardous failures.   

Achieving this objective requires a multi-disciplinary engineering effort that optimizes performance, minimizes weight, ensures economic feasibility, and meets safety requirements. The team shall develop innovative solutions to replicate, improve, or replace the current battery system.  By overcoming these challenges, the team aims to develop a custom battery solution that maximizes the car's competitive edge while ensuring safety and economic feasibility, ultimately enabling a successful entry in the SAE Electric Competition. 

<h3>Background </h3>

Electric vehicles (EVs) face significant challenges related to battery performance and safety. The large battery packs used in these vehicles have inherent limitations, including the potential risk of combustion, which can result in fires that are difficult to extinguish. 

A key requirement in the Formula SAE Electric competition is the battery discharge test, which reduces the battery to 10% of its overall charge. The battery system must be capable of completing this test and recharging safely without the risk of thermal events. To ensure safety and compliance, the battery management system (BMS) must effectively mitigate risks associated with overheating, overcharging, excessive discharge, extreme ambient temperatures, and improper storage conditions. 

The Spring 2025 capstone team is currently working on adapting Zero Motorcycle components for use in a Formula SAE race car. However, they are encountering significant challenges, particularly with the battery and BMS. As a result, this document primarily focuses on an alternative to this preexisting solution. 

<h3>Specifications and Constraints  </h3>

<h4>Specifications </h4>

The project specifications shall be defined by stakeholder requirements to ensure optimal performance and competitiveness. If any specification proves unattainable, discussions and negotiations with stakeholders shall be necessary to identify viable alternatives. The primary requirements include: 

1.) The battery may meet or exceed the performance of the Zero Motorcycle battery, ensuring sufficient power, endurance, and efficiency for competitive racing namely a maximum energy capacity of 7.2 kWh with a nominal energy capacity of 6.8 kWh, a nominal voltage of 102 V, a maximum cell discharge of 10 Coulombs, a maximum cell discharge temp of 60 degrees C, a maximum charge temperature of 50 degrees C, a minimum charge temperature of 0 degrees C, and a weight of 81 lbs. [12]

2.) Battery (accumulator): [11]

 - design of the battery shall be documented in the Structural Equivalency Spreadsheet (SES)  F.10.1.2 [11]

 - the battery pack shall attach to the vehicle. [11]

 - liquid coolant shall not touch the cells of the accumulator T.5.4.3 [11]

 - the hot (ungrounded) terminal shall be insulated T.9.2.3 [11]

 - the battery pack shall be made out of sturdy, NON-Flammable material T.9.2.5 [11]

 - the battery pack shall have documentation proving it meets the rules requirements. T.9.2.6 [11]

 - the maximum power shall not exceed 80 kW EV 3.3.1 [11]

 - maximum voltage between any two points shall not exceed 600 V DC. EV 3.3.2 [11]

 - the battery pack shall be connected to a motor controller, no direct connections between the battery and motor is allowed. EV 4.2 [11]

 - the battery pack shall be removable from the vehicle while still being rules compliant. EV.4.3.2 [11]

 - the battery pack shall be closed at all times without the need to install additional protective covers. EV.4.3.3 [11]

3.) The container may contain holes, but only the wiring harness, ventilation, fasteners, and coolant fluid may pass through those holes. EV.4.3.4 a [11]

4.) Each segment of the accumulator may have: [11]

 - a maximum voltage of 120 V DC.  [11]

 - energy of 6MJ maximum –figured by multiplying the maximum stack voltage with the nominal capacity of the cells used. 
   [11]

 - a mass of 12 kg maximum. [11]

 - the poles shall be insulated from the inner wall of the container with an insulating material rated for the maximum 
   voltage of the tractive system voltage. EV.5.2.2 a [11]

 - any penetrations of the container shall have protection against puncturing the insulating barrier. EV.5.2.2 c [11]

 - the outer container shall be connected to ground through a low resistance. EV.5.2.2 b [11]

 - each accumulator segment shall be electrically isolated from each other and on top of the segments to prevent arcing. 
   EV.5.2.3 [11]

5.) Each Accumulator Container shall be labeled with the EV.4.3.8: 
 - School Name and Vehicle Number
 - Symbol specified in ISO 7010-W012 (triangle with black lightning bolt on yellow background) with:
    a.) Triangle side length of 100 mm minimum
    b.) Visibility from all angles, including when the lid is removed
 - Text “Always Energized”
 - Text “High Voltage” if the voltage meets T.9.1.1(Any voltage more than 60 V DC or 25 V AC RMS) [11]
 - All wires in the accumulator shall be rated for the maximum voltage in the tractive system. EV.5.2.5 [11]

6.) Maintenance Plugs shall EV.5.3.2:  [11]

  - Require the physical removal or separation of a component. Contactors or switches are not acceptable Maintenance Plugs 
   [11]

  - Have access after opening the Accumulator Container and not necessary to move or remove any other components. [11]

  - Not be physically possible to make electrical connection in any configuration other than the design intended 
    configuration. [11]

  - Not require tools to install or remove. [11]

  - Include a positive locking feature which prevents the plug from unintentionally becoming loose. [11]
    
  - Be nonconductive on surfaces that do not provide any electrical connection [11]

7.) When the Accumulator Containers are opened or Segments are removed, the Accumulator Segments shall be separated by using the Maintenance Plugs. EV.5.3.3 [11]

8.) Isolation Relays - IR EV.5.4.1 All Accumulator Containers shall contain minimum one fuse (EV.6.6) and two or more Isolation Relays (IR) EV.5.4 [11]

9.) The Isolation Relays shall: a. Be a Normally Open type b. Open the two poles of the Accumulator EV.5.4.2 [11]

10.) When the IRs are open, High Voltage T.9.1.1 shall not be external of the Accumulator Container EV.5.4.3[11]

11.) The Isolation Relays and any fuses shall be separated from the rest of the Accumulator with an electrically insulated and Nonflammable Material (F.1.18). EV.5.4.4 [11]

12.) A capacitor may be used to hold the IRs closed for up to 250 ms after the Shutdown Circuit Opens EV.5.4.5 [11]

13.) Manual Service Disconnect - MSD A Manual Service Disconnect (MSD) shall be included to quickly disconnect one or the two poles of the Accumulator EV.11.3.2  EV.5.5 [11]

14.) The Energy Meter shall not be used as the Manual Service Disconnect (MSD) EV.5.5.2 [11]

15.) An Interlock EV.7.8 shall Open the Shutdown Circuit EV.7.2.2 when the MSD is removed EV.5.5.3 [11] 

16.) A dummy connector or similar may be used to restore isolation to meet EV.6.1. EV.5.5.4[11]

17.) Precharge and Discharge Circuits EV.5.6 [11]

18.) The Accumulator shall contain a Precharge Circuit. EV.5.6.1 [11]

19.) The Precharge Circuit shall: [11]

 - Be able to charge the Intermediate Circuit to minimum 90% of the Accumulator voltage before closing the second IR [11]

 - Be supplied from the Shutdown Circuit EV.7.1 [11]

20.) The Intermediate Circuit shall precharge before closing the second IR EV.5.6.2 [11]

 - The end of precharge shall be controlled by feedback by monitoring the voltage in the Intermediate Circuit [11]

 - The Tractive System shall contain a Discharge Circuit. EV.5.6.3 [11]

21.) The Discharge Circuit shall be:  [11]

 - Wired in a way that it is always active when the Shutdown Circuit is open  [11]

 - Able to discharge the Intermediate Circuit capacitors if the MSD has been opened  [11]

 - Not be fused  [11]

 - Designed to handle the maximum Tractive System voltage for minimum 15 seconds  [11]

22.) Positive Temperature Coefficient (PTC) devices shall not be used to limit current for the Precharge Circuit or Discharge Circuit EV.5.6.4 [11]

23.) The precharge relay shall be a mechanical type relay EV.5.6.5 [11]

24.) Voltage Indicator EV.5.7 [11]

25.) Each Accumulator Container shall have a prominent indicator when High Voltage T.9.1.1 is present at the vehicle side of the IRs  [11]

26.) The Voltage Indicator shall always function, including when the Accumulator Container is disconnected or removed EV.5.7.1 [11]

27.) The voltage being present at the connectors shall directly control the Voltage Indicator using hard wired electronics with no software control. EV.5.7.2 [11]

28.) The control signal which closes the IRs shall not control the Voltage Indicator EV.5.7.3 [11]

29.) The Voltage Indicator shall EV.5.7.4 :  [11]

  - Be located where it is clearly visible when connecting/disconnecting the Accumulator Tractive System connections  [11]

  - Be labeled “High Voltage Present” [11]

30.) Tractive System components and Accumulator Containers shall be protected from moisture, rain or puddles. A rating of IP65 is recommended EV.6.1.3 [11]

31.) Battery management system BMS [11]

- Prevents the maximum current draw from accumulator T.9.2.2 [11]

32.) Battery Management System - BMS EV.7.3 [11]

33.) A Battery Management System shall monitor the Accumulator(s) Voltage EV.7.4 and Temperature EV.7.5 when the EV.7.3.1:  [11]

 - Tractive System is Active EV.11.5  [11]

 - Accumulator is connected to a Charger EV.8.3  [11]

34.) The BMS shall have galvanic isolation at each segment to segment boundary, as approved in the ESF EV.7.3.2 [11]

35.) Cell balancing is not permitted when the Shutdown Circuit is Open ( EV.7.2, EV.8.4 ) EV.7.3.3[11]

36.) The BMS shall monitor for EV.7.3.4:  [11]

  - Voltage values outside the allowable range EV.7.4.2  [11]

  - Voltage sense Overcurrent Protection device(s) blown or tripped  [11]

  - Temperature values outside the allowable range EV.7.5.2  [11]

  - Missing or interrupted voltage or temperature measurements  [11]

  - A fault in the BMS  [11]

37.) If the BMS detects one or more of the conditions of EV.7.3.4 above, the BMS shall EV.7.3.5 :  [11]

  - Open the Shutdown Circuit EV.7.2.2  [11]

  - Turn on the BMS Indicator Light and the Tractive System Status Indicator EV.5.11.5 The two lights shall stay on until 
    the BMS is manually reset EV.7.2.3  [11]

38.) The BMS Indicator Light shall be EV.7.3.6:  [11]

  - Color: Red  [11]

  - Clearly visible to the seated driver in bright sunlight  [11]

  - Clearly marked with the lettering “BMS” [11]

39.) Accumulator Voltage EV.7.4  [11]

40.) The BMS shall measure the cell voltage of each cell When single cells are directly connected in parallel, only one voltage measurement is needed EV.7.4.1 [11]

41.) Cell Voltage levels shall stay inside the allowed minimum and maximum cell voltage levels stated in the cell data sheet. Measurement accuracy shall be considered. EV.7.4.2 [11]

42.) All voltage sense wires to the BMS shall meet one of EV.7.4.3:  [11]

  - Have Overcurrent Protection EV.7.4.4 below  [11]

  - Meet requirements for no Overcurrent Protection listed in EV.7.4.5 below  [11]

43.) When used, Overcurrent Protection for the BMS voltage sense wires shall meet the two EV.7.4.4:  [11]

  - The Overcurrent Protection shall occur in the conductor, wire or PCB trace which is directly connected to the cell 
    tab.  [11]

  - The voltage rating of the Overcurrent Protection shall be equal to or higher than the maximum segment voltage  [11]

44.) Overcurrent Protection is not required on a voltage sense wire if all three conditions are met EV.7.4.5:  [11]

 - BMS is a distributed BMS system (one cell measurement per board) [11]

 - Sense wire length is less than 25 mm  [11]

 - BMS board has Overcurrent Protection [11]

45.) Accumulator Temperature EV.7.5 [11]

46.) The BMS shall measure the temperatures of critical points of the Accumulator EV.7.5.1 [11]

47.) Temperatures (considering measurement accuracy) shall stay below the lower of the two EV.7.5.2:  [11]

 - The maximum cell temperature limit stated in the cell data sheet  [11]

 - 60°C [11]

48.) Cell temperatures shall be measured at the negative terminal of the respective cell EV.7.5.3 [11]

 

49.) The temperature sensor used shall be in direct contact with one of EV.7.5.4:  [11]

  - The negative terminal itself  [11]

  - The negative terminal busbar less than 10 mm away from the spot weld or clamping source on the negative cell terminal  
    [11]

50.) For lithium based cells, EV.7.5.5  [11]

  - The temperature of a minimum of 20% of the cells shall be monitored by the BMS  [11]

  - The monitored cells shall be equally distributed inside the Accumulator Container(s) The temperature of each cell 
    should be monitored [11] 

51.) Multiple cells may be monitored with one temperature sensor, if EV.7.5 is met for all cells sensed by the sensor. EV.7.5.6 [11]

52.) Temperature sensors shall have appropriate electrical isolation that meets one of the two EV.7.5.7:  [11]

  - Between the sensor and cell  [11]

  - In the sensing circuit [11]

53.) The isolation shall consider GLV/TS isolation as well as common mode voltages between sense locations. [11]
  
54.) The battery shall safely discharge and recharge only under appropriate operating conditions (when the internal battery temperature is between -4 degrees Fahrenheit and 140 degrees Fahrenheit) to minimize the risk of combustion and otherwise be disconnected.

55.) The battery shall disconnect based on the means of abnormalities: high temperature, high current, high voltage. 

56.) The battery shall have a total cost ,manufactoring and design, not exceeding $10,000. 
  
57.) All electrical components, including accumulator cells, shall be sheilded from exposure to water.

58.) The battery must be covered in non-flammable material.[11] 

<h4>Constraints </h4>

Electric vehicles (EVs) and their battery systems are subject to various regulatory, technical, and safety constraints. These constraints are designed to ensure the safety, reliability, and environmental sustainability of EVs. Key constraints include: 

1. Safety Regulations
  * To prevent thermal runaway, the Battery Management System (BMS) shall monitor temperature in compliance 
    with UN 38.3 and SAE J2929.
  * The battery shall withstand impact forces without causing fires or leaks, meeting the requirements of FMVSS 305 and 
    UNECE R100.
  * To prevent dust and water exposure, the battery shall be encapsulated in accordance with IEC 60529 at an IP65 level.
  * The battery shall include overcurrent and overvoltage protection to prevent hazardous conditions caused by short 
    circuits or voltage spikes in the form of the precharge circuit and discharge circuit.[11]
2. Performance Standards
  * The BMS shall continuously monitor the battery’s State of Charge (SoC) and State of Health (SoH) in compliance with 
    SAE J1939 and ISO 15118.
3. Environmental & Recycling Regulations
  * The battery shall comply with EU Battery Directive (2006/66/EC) and the U.S. Battery Act (42 U.S.C. § 14301) for 
    disposal and recycling.
  * The battery shall not contain restricted heavy metals such as lead, cadmium, and mercury.

<h3>Survey of Existing Solutions: </h3>

Currently, various methods exist for implementing a battery management system. The Zero Motorcycle battery includes a proprietary BMS but integrating it into the current vehicle shall require modifications. Additionally, much of the motorcycle’s original system is no longer available, complicating the adaptation process.  

If the team decides to design a new battery, a custom BMS shall be required to prevent suboptimal operating conditions, overheating, and battery damage. A new battery costs ~$15,000 [13]. Therefore, the team stands to not only own the design of their BMS and battery combination, but also save money in the process. 

Alternative options include purchasing pre-built batteries from major manufacturing companies supporting the Formula SAE competition. However, these batteries pose several challenges, including increased weight and integration complexities. Regardless of the battery selection, a dedicated BMS shall be necessary to mitigate fire risks and ensure compliance with Formula SAE regulations and tests.  

 

<h3>Measure of Success:</h3>  

The project’s success shall be evaluated based on the following criteria: 

* Development of a BMS that effectively monitors and regulates battery performance. 

* Achievement of a power-to-weight ratio that meets or exceeds competition requirements. 

* Compliance with all safety regulations and successful mitigation of potential hazards. 

* Completion of a fully functional and testable BMS for the Formula SAE Car.  

<h3>Resources:  </h3>

<h4>Budget </h4>

The estimated cost to build the battery is approximately $4,282, while the E-bike itself cost around $15,000 [13]. However, due to the resource constraints, the project team shall adhere to a strict budget, minimizing excess material costs and maximizing the use of available resources. The team shall track expenditures carefully to maintain cost efficiency. 

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

Battery Cost Calculation: 
Power required for SAE Car: 64 Ah * 102 V = 6.5 kWh
Power produced by each individual battery cell: 3.6V * 5 Ah = 18 Wh
6.5 kWh / 18 Wh = 361.1111

BMS Cost Calculation:
PCB Design and Construction: ~$600
Components on PCB: ~$300
Misc: ~$100

<h3>Personnel </h3>

The team comprises five dedicated members who shall work extensively to bring the project as close to completion as possible: 

Joseph Dylan Caten – C++, C, Assembly, Python, Digital Logic, VHDL 

Maddox Cagle – LTSpice, Soldering, Wiring, Project Management 

Jordan Davis – AutoCAD, SolidWorks, LTSpice, Soldering, Digital Logic 

Marisol Miranda – C++, C, LTSpice, MATLAB, VHDL, Assembly, AutoCAD 

Mackenzie Raleigh - C++, Python, C, LTSpice

The team shall collaborate with the ECE Capstone II group which has been working on this project since Fall 2024 and a newly assigned ME Team. This collaboration shall facilitate knowledge transfer and enhance project efficiency.  Additionally, having a defined customer, supervisors, and instructor shall allow the team to focus on the project’s objectives from the outset. 

Micah Rentschler – Instructor and Customer Representative for the ECE Department 

Mark Davis – Supervisor and Automotive Shop Technician 

Dr. Andy Pardue – Supervisor of the collaborating Mechanical Engineering Team 

 

<h3>Timeline </h3> 

The project shall run until December 2025. The primary objectives include recreating the E-bike battery from scratch, improving upon the existing system, and developing a functional BMS. If the team can achieve a working BMS and prepare the car for operation, the project goals shall be considered accomplished.   

January – May 2025: Design Project and learn from parallel capstone group 

August – December 2025: Build new Battery. Develop functional BMS. Prepare car to drive. 

Detailed layout of project development: 

Spring 2025 – Fall 2025: 

January: Groups are formed, and project is given. 

February: Project research begins. Project proposal is created for further development. 

March: Design of project continues. Timeline begins to be put in place for next semester. 

April: Begin to work thoroughly along side graduating group to pick up where they left off. 

May: Documentation and project design is put completely in place. Everything is developed as much as possible for manufacturing in the fall. A jump start on buying parts for the fall is a goal for our team. Time will need used as efficiently as possible. 

August: Project is picked up for build to begin. Components are ordered as much in advance as possible. 

September – December: Build and design come together to create our project.  

December: Project is finished. Car is ready to drive. BMS is constructed. Final presentation is given. 

<img src= "/images/projectproposalgantt4.PNG" witdth="8000" height="400">
 

 

<h3>Specific implication: </h3>  

The implementation of a BMS will provide significant benefits to the Formula SAE Electric Car team, directly enhancing performance, safety, and efficiency to improve race results. By optimizing energy distribution, the BMS will ensure that each cell operates within its optimal parameters, meeting both efficiency and regulatory requirements. This leads to better energy utilization, allowing the car to maximize power output and driving range. Additionally, the vehicle shall maintain consistent performance throughout the race, even under varying power demands such as acceleration and cornering. 

Safety is a critical factor in a competitive racing environment. The BMS will continuously monitor key parameters such as battery state of charge and temperature. With real-time protective measures against undercharge, and thermal anomalies, the system significantly reduces the risk of battery failure and completely prevents overheating or other fire hazards. This shall ensure not only the safety of the vehicle but also the protection of the driver in the advent of an incident.  

The BMS shall also enhance energy efficiency by actively managing charge and discharge cycles, ensuring that the car maintains peak power throughout the race. Furthermore, it will extend the battery pack’s lifespan, reducing the frequency and cost of replacements-an important financial consideration for the team. Real-time telemetry provided by the BMS will enable the team to analyze battery performance, optimize energy consumption, and make data-driven adjustments for improved efficiency. The system’s ability to fine-tune performance settings and conserve battery power when necessary   

<h3>Broader Implications, Ethics, and Responsibility as Engineers: </h3> 

The project shall consider the broader ethical and environmental implications of battery-powered electric vehicles. While EVs reduce greenhouse gas emissions, battery production and disposal raise ethical concerns, including environmental degradation, labor exploitation, and improper waste management. 

To address these concerns, engineers shall work with policymakers to enforce stricter environmental and social standards in mining operations. Research into advanced battery recycling technologies shall be prioritized to improve lithium-ion battery reuse and reduce reliance on newly mined materials. Additionally, enhancing battery designs, enforcing regulations, and promoting fire prevention measures shall mitigate safety risks associated with lithium-ion batteries. 

Engineers have a responsibility to develop sustainable solutions that prioritize ethical sourcing, minimize environmental harm, and advocate for fair labor practices. The team shall ensure safe handling, storage, and disposal of battery components while remaining aware of broader sustainability issues. 

<h3>References</h3> 

[1]“2025 Formula SAE Rules V.1 are now available,” Fsaeonline.com, 2024. https://www.fsaeonline.com/cdsweb/app/NewsItem.aspx?NewsItemID=379e4a8a-80a2-4a74-87c2-6f2de4212270 

[2]“Formula SAE Electric 2024 Overall Results.” Available: https://www.sae.org/binaries/content/assets/cm/content/attend/student-events/results/formula-sae/fsae_ev_2024_results.pdf 

[3] I. Morse, “Who gave the battery such power?,” NOEMA, https://www.noemamag.com/who-gave-the-battery-such-power/ (accessed Feb. 16, 2025).  

[4] T. C. Frankel, “Cobalt mining for lithium ion batteries has a high human cost,” The Washington Post, https://www.washingtonpost.com/graphics/business/batteries/congo-cobalt-mining-for-lithium-ion-battery/ (accessed Feb. 17, 2025). 

[5] E. Quijano, “Fatal fires serve as cautionary tale of dangers of lithium-ion batteries,” CBS News, https://www.cbsnews.com/news/lithium-ion-batteries-dangers-warning-fatal-fires-new-york-city/ (accessed Feb. 16, 2025). 

[6] H. Ritchie, “Is cobalt the blood diamond of electric cars? What can be done about it?” Sustainability by Numbers, https://www.sustainabilitybynumbers.com/p/cobalt (accessed Feb. 17, 2025). 

[7] M. Ants, “Health hazards of improper lithium-ion battery disposal,” BatX Energies, https://batxenergies.com/health-hazards-of-improper-lithium-ion-battery-disposal/ (accessed Feb. 17, 2025). 

[8] D. Nichols, “Environmental impact of EV Batteries: GreenCars,” GreenCars, https://www.greencars.com/greencars-101/environmental-impact-of-ev-batteries#:~:text=Each%20ton%20of%20refined%20lithium,%2C%20wildlife%20habitats%2C%20and%20groundwater. (accessed Feb. 17, 2025). 

[9] Zero Motorcycle 2016 Owner’s Manual. Zero Motors, 2016. 

[10] S. J. Moura, N. A. Chaturvedi, and M. Krstic, “Constraint management in Li-ion batteries: A modified reference governor approach,” American Control Conference, vol. 1, pp. 5332–5337, Jun. 2013, doi: https://doi.org/10.1109/acc.2013.6580670. 

[11] Formula SAE Rules 2025, Formula SAE, 2025 

[12] "Zero Motors Cypher 2 Powertrain Datasheet," Source.[Online] Available: https://zero-cms-disco.cdn.prismic.io/zero-cms-disco/372e4e04-53f3-4f30-9bf2-7e3e5fc1a901_powertrain-data-sheet.pdf

[13] “Zero Motorcycles S - Electric Motorcycle Company,” Zeromotorcycles.com, 2025. https://zeromotorcycles.com/model/zero-s (accessed Mar. 12, 2025).
‌

<h3>‌Statement of Contributions </h3>

Jordan Davis: Problem Formulation section. 

Dylan Caten: Survey of Existing Solutions section. 

Maddox Cagle: Resources section. 

Marisol Miranda: Broader Implications and Responsibilities as Engineers section. 

Mackenzie Raleigh: Introduction and Specific Implementations section. 

 
