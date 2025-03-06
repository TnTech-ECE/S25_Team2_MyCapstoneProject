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

* The battery shall meet or exceed the performance of the Zero Motorcycle battery, ensuring sufficient power, endurance, and efficiency for competitive racing. 

* The battery shall safely discharge and recharge under appropriate operating conditions without the risk of combustion. 

* This project shall employ a strategic engineering approach that optimally balances performance, weight, safety, and cost efficiency. 

* The battery shall have a total cost not exceeding $10,000. 

* All electrical components shall be designed to be waterproof, ensuring protection against moisture and environmental exposure. 

<h4>Constraints </h4>

* The project shall adhere to external constraints, including: 

* The battery management system shall display the voltage levels and other relevant information as given by the Formula SAE rulebook and shut down the operation of the battery to prevent fires when those conditions are not met.[11] 

* The battery must be covered in non-flammable material.[11] 

<h4> Economic feasibility and resource limitations.</h4>  

The constraints explicitly model specific degradation mechanisms, such as lithium plating, lithium depletion, overheating, and stress fracture. A critical challenge is that these states evolve according to a systems of nonlinear partial differential equations and are not physically measurable [10]. This project shall address this challenge by utilizing the reference governor concept, demonstrating how electrochemical model state information can be leveraged to ensure safe operation while enhancing energy capacity, power, and charge times in Li-ion batteries [10]. 

 

<h3>Survey of Existing Solutions: </h3>

Currently, various methods exist for implementing a battery management system. The Zero Motorcycle battery includes a proprietary BMS but integrating it into the current vehicle shall require modifications. Additionally, much of the motorcycle’s original system is no longer available, complicating the adaptation process.  

If the team decides to design a new battery, a custom BMS shall be required to prevent suboptimal operating conditions, overheating, and battery damage.  

Alternative options include purchasing pre-built batteries from major manufacturing companies supporting the Formula SAE competition. However, these batteries pose several challenges, including increased weight and integration complexities. Regardless of the battery selection, a dedicated BMS shall be necessary to mitigate fire risks and ensure compliance with Formula SAE regulations and tests.  

 

<h3>Measure of Success:</h3>  

The project’s success shall be evaluated based on the following criteria: 

* Development of a BMS that effectively monitors and regulates battery performance. 

* Achievement of a power-to-weight ratio that meets or exceeds competition requirements. 

* Compliance with all safety regulations and successful mitigation of potential hazards. 

* Completion of a fully functional and testable BMS for the Formula SAE Car.  

<h3>Resources:  </h3>

<h4>Budget </h4>

The estimated cost to build the battery is approximately $4,676, while the E-bike itself cost around $10,000. However, due to the resource constraints, the project team shall adhere to a strict budget, minimizing excess material costs and maximizing the use of available resources. The team shall track expenditures carefully to maintain cost efficiency. 

|Item/Material | Quantity | Cost(USD) | 
|--------------|----------|-----------|
|Lithium Battery Total| 361 | >~$2,176|
|Battery Construction Components| ~ |>~1,000|
|BMS Components| 1 | >~$1,000| 
|Wire and Connectors| <1 |~$500|
|Total| |~$4,676|
 

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

<img src= "/images/projectproposalgantt3.PNG" witdth="8000" height="400">
 

 

<h3>Specific implication: </h3>  

The implementation of a BMS will provide significant benefits to the Formula SAE Electric Car team, directly enhancing performance, safety, and efficiency to improve race results. By optimizing energy distribution and balancing battery cells, the BMS will ensure that each cell operates within its optimal parameters, meeting both efficiency and regulatory requirements. This leads to better energy utilization, allowing the car to maximize power output and driving range. Additionally, the vehicle shall maintain consistent performance throughout the race, even under varying power demands such as acceleration and cornering. 

Safety is a critical factor in a competitive racing environment. The BMS will continuously monitor key parameters such as battery state of charge and temperature. With real-time protective measures against overcharge, undercharge, and thermal anomalies, the system significantly reduces the risk of battery failure and completely prevents overheating or other fire hazards. This shall ensure not only the safety of the vehicle but also the protection of the driver in the advent of an incident.  

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

<h3>‌Statement of Contributions </h3>

Each team member will document their individual contributions to the project proposal. This ensures transparency and accountability, certifying that all team members have made meaningful contributions to the report and project development.  

Jordan Davis: Problem Formulation section. 

Dylan Caten: Survey of Existing Solutions section. 

Maddox Cagle: Resources section. 

Marisol Miranda: Broader Implications and Responsibilities as Engineers section. 

Mackenzie Raleigh: Introduction and Specific Implementations section. 

 
