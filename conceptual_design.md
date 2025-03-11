<h1>Conceptual Design: Battery Management System  

Formula SAE Electric Car Team</h1> 

<h3>Team 2: Maddox Cagle, Jordan Davis, Mackenzie Raleigh, Marisol Miranda, Dylan Caten </h3>

 

 

 

<h2>Introduction:  </h2>

The development of a custom Battery Management System (BMS) for the Formula SAE Electric Car is a crucial step toward ensuring optimal battery performance, safety, and longevity. The primary goal of this project is to create a BMS that monitors battery state, prevents hazardous failures, complies with Formula SAE safety regulations and passes the tests necessary. This document outlines the conceptional design, including the original problem formulation, solution decompositions, specifications, constraints, and an implementation roadmap for the custom BMS.  

 

<h2>Restating the Fully Formulated Problem:  </h2>

A well-designed BMS is essential for preventing battery fire in environments. The system must regulate charge levels, monitor temperature, provide cell balancing, and shut down under unsafe conditions. The formulated problem includes the following “shall” statements: 

*The BMS shall monitor the battery’s state of charge and state of health in real-time. 

*The system shall prevent overcharging, excessive discharge, and overheating. 

*The BMS shall include an automatic shutdown mechanism to reduce safety risks under the following conditions, temperatures bellow -4 degrees Fahrenheit, temperatures at or above 140 degrees Fahrenheit, low charge, excessive discharging, and when overcharging. 

*The system shall integrate with the car’s existing electrical architecture and Formula SAE regulations. 

*The total project cost shall not exceed $10,000, ensuring cost-effectiveness. 

<h2>Constraints and Their Origins </h2>

The design of the BMS must adhere to several constraints imposed by competition rules, engineering standards, and fire safety concerns. These include: 

*Safety Regulations: The BMS must comply with Formula SAE safety standards, including fire prevention and automatic shutdown in hazardous conditions as stated above. 

*Material Constraints: The battery must be enclosed in non-flammable housing to meet industry and competition safety guidelines. 

*Economic Feasibility: The total cost must remain under budget to ensure financial viability and to score well in the cooresponding Formula SAE test.  

*Technical Compatibility: The BMS must be compatible with the vehicle’s electrical system which is currently being designed for the Zero Motor's battery, ensuring seamless integration. 

<h2>Comparative Analysis of Potential Solutions- Dylan </h2>

While this team could solve the battery management system of the Zero Motor’s 2022 battery, this project is already being developed by the current ECE capstone team. As such, this is not an option for this group. 

A variety of different battery options are available, however, the current vehicle under design is made assuming that the Zero Motor battery will be used in it. This requires the group to get a certain voltage and energy density is a predetermined area.
To compensate for this the group shall use similar materials to the Zero Motor battery. This will allow the group to mimic the electrical characteristics with proper cell placement.
It does mean, however, that this group shall implement its own battery management system that shall be of a similar size to Zero Motor’s battery management system, which will require the design to be optimal in both size and charge per area. 

Formula SAE does require some constraints placed upon accumulators built by students, namely for fireprotection. These constraints, including cell monitoring, voltage regulation, voltage reading, current limiting, charging and discharging control must be implimented to reduce the risk of fire hazards.

 

High-Level Solution:  Dylan and Marisol 

This section presents a comprehensive, high-level solution aimed at efficiently fulfilling all specified requirements and constraints. The solution is designed to maximize stakeholder goal attainment, adhere to established constraints, minimize risks, and optimize resource utilization. Please elaborate on how your design accomplishes these objectives. 
Additionally, this group must design the BMS and battery to comply with Formula SAE rules.
 

This team shall design a battery that has similar electrical and volume characteristics to the 2022 Zero Motor’s motorcycle battery with a knowable battery management system to be used as a backup for the Formula SAE event. 

<h2>Hardware Block Diagram </h2>

Block diagrams are an excellent way to provide an overarching understanding of a system and the relationships among its individual components. Generally, block diagrams draw from visual modeling languages like the Universal Modeling Language (UML). Each block represents a subsystem, and each connection indicates a relationship between the connected blocks. Typically, the relationship in a system diagram denotes an input-output interaction. 

In the block diagram, each subsystem should be depicted by a single block. For each block, there should be a brief explanation of its functional expectations and associated constraints. Similarly, each connection should have a concise description of the relationship it represents, including the nature of the connection (such as power, analog signal, serial communication, or wireless communication) and any relevant constraints. 

The end result should present a comprehensive view of a well-defined system, delegating all atomic responsibilities necessary to accomplish the project scope to their respective subsystems. 

 ![image](https://github.com/user-attachments/assets/44d1f0d5-974d-433c-85c3-95a8f3e58d2c)


<h2>Operational Flow Chart </h2>

Similar to a block diagram, the flow chart aims to specify the system, but from the user's point of view rather than illustrating the arrangement of each subsystem. It outlines the steps a user needs to perform to use the device and the screens/interfaces they will encounter. A diagram should be drawn to represent this process. Each step should be represented in the diagram to visually depict the sequence of actions and corresponding screens/interfaces the user will encounter while using the device. 

![Capstone_I_ConceptualDesign_Flowchart1](https://github.com/user-attachments/assets/f7fd3949-ff1b-418a-b5cb-52538a6ff7fd)


<h2>Atomic Subsystem Specifications: Jordan </h2>

Based on the high-level design, provide a comprehensive description of the functions each subsection will perform. 

Include a description of the interfaces between this subsystem and other subsystems: 

Give the type of signal (e.g. power, analog signal, serial communication, wireless communication, etc). 

Clearly define the direction of the signal (input or output). 

Document the communication protocols used. 

Specifying what data will be sent and what will be received. 

Detail the operation of the subsystem: 

Illustrate the expected user interface, if applicable. 

Include functional flowcharts that capture the major sequential steps needed to achieve the desired functionalities. 

For all subsystems, formulate detailed "shall" statements. Ensure these statements are comprehensive enough so that an engineer who is unfamiliar with your project can design the subsystem based on your specifications. Assume the role of the customer in this context to provide clear and precise requirements. 

 

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

 

<h2>Division of Labor </h2>

First, conduct a thorough analysis of the skills currently available within the team, and then compare these skills to the specific requirements of each subsystem. Based on this analysis, appoint a team member to take the specifications for each subsystem and generate a corresponding solution (i.e. detailed design). If there are more team members than subsystems, consider further subdividing the solutions into smaller tasks or components, thereby allowing each team member the opportunity to design a subsystem. 

 

<h2>Timeline </h2>

Revise the detailed timeline (Gantt chart) you created in the project proposal. Ensure that the timeline is optimized for detailed design. Address critical unknowns early and determine if a prototype needs to be constructed before the final build to validate a subsystem. Additionally, if subsystem A imposes constraints on subsystem B, generally, subsystem A should be designed first. 

 

<h2>References </h2>

All sources utilized in the conceptual design that are not considered common knowledge must be properly cited. Multiple references should be included. 

 

<h2>Statement of Contributions </h2>

Each team member is required to make a meaningful contribution to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate. 

Each team member is required to make a meaningful contribution to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate. 
