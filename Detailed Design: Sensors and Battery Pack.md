<h1>Detailed Design: Sensors and Battery Cells</h1>

<h2>Function of the Subsystem</h2>
<br/> 
The Formula SAE vehicle requires a battery similar to the Zero Motor's battery in electrical characteristics in order to function properly. Namely, the output voltage should be 102 volts with a nominal energy capacity of 6.3 kwh.
*Formula SAE has a number of rules regarding the battery cells and sensors, namely: 
--
*additionally we would like, 
--Keep the dimensions similar to the Zero Motor's battery -- this may not be possible.
--Keep the price of the project at a reasonable level, below $10,000 for this detailed design.

<h3> Sensors and Battery Cells Integration </h3>
The battery cells and sensors are embeded in the accumulator behind a layer of insulation that hooks up to an isolation relay and outputs a steady low power voltage for the low powered systems and a high power voltage which can be turned off by the battery management system (BMS).

<h2> Specifications and Constraints </h2>

<h3> Constraints </h3>

* Each segment of the accumulator must weigh no more than 12 kg
  
* Each segment must have insulation rated for the maximum voltage of the accumulator
  
* 20% of all cells must be monitored for temperature at the negative terminal
  
* 20% of all cells must be monitored for voltage

<h3> Specifications </h3>

* The electrical characteristics should be similar to the Zero Motor's battery
  
* The size of the resulting battery should be the same as the Zero Motor's battery

<h2> Proposed Solution </h2>

![image](https://github.com/user-attachments/assets/821f508c-f054-4671-96f8-e4483e261d65)

We want to use Enepaq's Li-ion building block with Molicel P42A modules 1s7p in a series configuration of thirty units and two in parallel to get a 30s14p configuration.
To meet the requirements in terms of weight the cells will be in four segments of fifteen cells in series with seven in parallel, seperated by maintanence plugs resulting in a weight of 7.905 kg per segment. 

that will have the electrical characteristics 

* 108 volts

* 6,348 Wh

* 1,764 Ah

-total weight : 69.10 pds 

and will have a cost of $6,973.20 before tarrifs, shipping, and handling.

The modules will be hooked up with Enepaq's provided busbar and bolt kits to achieve this configuration. The busbar and bolt kits will also satisfy the maintenance plug requirements for Formula SAE.

<h2>Interface with other subsystems</h2>

The battery cells are always at their output voltage unless they are not and need to be charged. All electrical components of the vehicle can trace their power back to the cells. Specifically, the cells interface with the voltage indicator and isolation relay.
The temperature sensors communicate directly to the BMS to determine the battery operation. The BMS must measure the voltage of the cells at their terminals to determine cell health, the Enepaq modules do not do this function. 

<h2>Flowchart</h2>

![image](https://github.com/user-attachments/assets/0b821e7c-6e81-4cd3-ad46-b0b9e70dc31c)


<h2>Bill of Materials</h2>

|Item|Quantity|price per unit|price total|
|----|-----|----|----|
|1s7p|60|$116.84| $7010.40|

<h2>Analysis</h2>
<h3>Relevant Rules and Rule Numbers</h3>

EV.1.1 Tractive System – TS  
Every part electrically connected to the Motor(s) and/or Accumulator(s) 

EV.1.2 Grounded Low Voltage - GLV
Every electrical part that is not part of the Tractive System 

EV.1.3 Accumulator  
All the battery cells or super capacitors that store the electrical energy to be used by the 
Tractive System

EV.2.1.1 Each team must submit an Electrical System Form (ESF) with a clearly structured 
documentation of the entire vehicle electrical system (including control and Tractive System). 
Submission and approval of the ESF does not mean that the vehicle will automatically pass 
Electrical Technical Inspection with the described items / parts.

EV.3.3.1 The maximum power measured by the Energy Meter must not exceed 80 kW  
 
EV.3.3.2 The maximum permitted voltage that may occur between any two points must not exceed 
600 V DC

EV.5.1.2 Each Accumulator Segment must contain: 
• Static voltage of 120 V DC maximum 
• Energy of 6 MJ maximum 
The contained energy of a stack is calculated by multiplying the maximum stack voltage 
with the nominal capacity of the used cell(s) 
• Mass of 12 kg maximum 

EV.5.3.1 Maintenance Plugs must allow electrical separation of the Accumulator Segments to meet:  
a. The separated Segments meet voltage and energy limits of EV.5.1.2
 
b. The separation must affect the two poles of the Segment 

EV.5.3.2 Maintenance Plugs must: 

a. Require the physical removal or separation of a component.  Contactors or switches are 
not acceptable Maintenance Plugs  

b. Have access after opening the Accumulator Container and not necessary to move or 
remove any other components 

c. Not be physically possible to make electrical connection in any configuration other than 
the design intended configuration

d. Not require tools to install or remove

e. Include a positive locking feature which prevents the plug from unintentionally becoming 
loose 

f. Be nonconductive on surfaces that do not provide any electrical connection 

EV.5.3.3 When the Accumulator Containers are opened or Segments are removed, the Accumulator 
Segments must be separated by using the Maintenance Plugs

EV.6.3.1 All wires and terminals and other conductors used in the Tractive System must be sized for the 
continuous current they will conduct  
EV.6.3.2 All Tractive System wiring must: 
a. Be marked with wire gauge, temperature rating and insulation voltage rating.  
A serial number or a norm printed on the wire is sufficient if this serial number or norm is 
clearly bound to the wire characteristics for example by a data sheet. 
 
b. Have temperature rating more than or equal to 90°C

EV.6.3.3 Tractive System wiring must be: 

a. Done to professional standards with sufficient strain relief  

b. Protected from loosening due to vibration  

c. Protected against damage by rotating and / or moving parts 

d. Located out of the way of possible snagging or damage  



EV.6.3.4 Any Tractive System wiring that runs outside of electrical enclosures:  
a. Must meet one of the two: 

• Enclosed in separate orange nonconductive conduit  

• Use an orange shielded cable  

b. The conduit or shielded cable must be securely anchored at each end to allow it to 
withstand a force of 200 N without straining the cable end crimp 

c. Any shielded cable must have the shield grounded 

EV.6.6.2 Unless otherwise allowed in the Rules, all Overcurrent Protection devices must: 

a. Be rated for the highest voltage in the systems they protect.  
Overcurrent Protection devices used for DC must be rated for DC and must carry a DC 
rating equal to or more than the system voltage  

b. Have a continuous current rating less than or equal to the continuous current rating of 
any electrical component that it protects  

c. Have an interrupt current rating higher than the theoretical short circuit current of the 
system that it protects  


EV.6.6.3 Each parallel element of multiple parallel battery cells, capacitors, strings of battery cells, 
strings of capacitors, or conductors must have individual Overcurrent Protection. 

EV.6.6.4 Any conductors (wires, busbars, etc) conducting the entire pack current must meet one of: 
a. Be appropriately sized for the total current that the individual Overcurrent Protection 
devices could transmit 

b. Contain additional Overcurrent Protection to protect the conductors

EV.7.5.1 The BMS must measure the temperatures of critical points of the Accumulator 

EV.7.5.2 Temperatures (considering measurement accuracy) must stay below the lower of the two: 

• The maximum cell temperature limit stated in the cell data sheet 

• 60°C 

EV.7.5.3 Cell temperatures must be measured at the negative terminal of the respective cell

EV.7.5.4 The temperature sensor used must be in direct contact with one of:  

• The negative terminal itself  

• The negative terminal busbar less than 10 mm away from the spot weld or clamping 
source on the negative cell terminal 

EV.7.5.5 For lithium based cells, 

a. The temperature of a minimum of 20% of the cells must be monitored by the BMS  

b. The monitored cells must be equally distributed inside the Accumulator Container(s)  
The temperature of each cell should be monitored

<h3> Other Options for Battery Cells</h3>

BL5000C21703S3PFTM106ICC1NN

BATTERY PACK LI-ION 10.8V 21700

from GlobTek, inc

<h4>Pros</h4>

* significantly cheaper than the Enepaq modules.

* requires only 40 units to impliment

* similar electrical characteristics to the enepaq solution

* lighter weight

* Contains the relevant temperature sensors

<h4>Cons</h4>

* There are only 30 units of this battery module available.

* The battery cell used in this module is made in China which is currently being tarrifed. It is unlikely more of the cell will be made available soon.

* Considerably more work would have to be placed in configuring and assembling the packs into the required 10s4p configuration required.

* This solution requires its own insulation for the cells.

Generic Battery Pack from Enepaq

<h4>Pros</h4>

* No quote needed for purchasing

* Same product as the molicel battery packs but with a different cell.

<h4>Cons</h4>

* Older model batteries, requires more modules and has weaker preformance.

* Vastly more expensive, over $40,000 for the battery packs alone.



<h2>References</h2>

[1] "Zero Motors Cypher 2 Powertrain Datasheet," Source.[Online] Available: https://zero-cms-disco.cdn.prismic.io/zero-cms-disco/372e4e04-53f3-4f30-9bf2-7e3e5fc1a901_powertrain-data-sheet.pdf

[2] Formula SAE Rules 2025, Formula SAE, 2025.

[3] Enepaq. "Li-ion building block with Molicel P45B datasheet." enepaq.com. https://enepaq.com/wp-content/uploads/2025/02/Molicel-P45B-21700-Li-ion-Battery-Module-With-Temperature-Sensor-Datasheet-.pdf (Accessed May 7, 2025).

[4] GlobTek. "U5M3183792." spec.globtek.info. https://spec.globtek.info/spec/pdf/2765989/U5M3183792 (Accessed May 7, 2025).

