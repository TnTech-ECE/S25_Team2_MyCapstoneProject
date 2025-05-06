<h1> Detailed Design: Sensors and Battery Cells </h1>
The Formula SAE vehicle requires a battery similar to the Zero Motor's battery in electrical characteristics in order to function properly. Namely, the output voltage should be 102 volts with a nominal energy capacity of 6.3 kwh.
*Formula SAE has a number of rules regarding the battery cells and sensors, namely: 
--
*additionally we would like, 
--Keep the dimensions similar to the Zero Motor's battery -- this may not be possible.
--Keep the price of the project at a reasonable level, below $10,000 for this detailed design.

<h3> Sensors and Battery Cells Integration </h3>
The battery cells and sensors are embeded in the accumulator behind a layer of insulation that hooks up to an isolation relay and outputs a steady low power voltage for the low powered systems and a high power voltage which can be turned off by the battery management system (BMS).

<h3> Constraints </h3>

* Each segment of the accumulator must weigh no more than 12 kg
  
* Each segment must have insulation rated for the maximum voltage of the accumulator
  
* 20% of all cells must be monitored for temperature at the negative terminal
  
* 20% of all cells must be monitored for voltage

<h3> Specifications </h3>

* The electrical characteristics should be similar to the Zero Motor's battery
  
* The size of the resulting battery should be the same as the Zero Motor's battery

<h2> Proposed Solution </h2>
We want to use Enepaq's Li-ion building block with Molicel P42A modules 1s7p in a series configuration of thirty units and two in parallel to get a 30s14p configuration.
To meet the requirements in terms of weight the cells will be in four segments of fifteen cells in series with seven in parallel, seperated by maintanence plugs resulting in a weight of 7.905 kg per segment. 


that will have the electrical characteristics 

*108 volts

*6,348 Wh

*1,764 Ah

-total weight : 69.10 pds 

and will have a cost of $6,973.20 before tarrifs, shipping, and handling.
The modules will be hooked up with Enepaq's provided busbar and bolt kits to achieve this configuration.

<h2>Interface with other subsystems</h2>

The battery cells are always at their output voltage unless they are not and need to be charged. All electrical components of the vehicle can trace their power back to the cells. Specifically, the cells interface with the voltage indicator and isolation relay.
The temperature sensors communicate directly to the BMS to determine the battery operation. The BMS must measure the voltage of the cells at their terminals to determine cell health, the Enepaq modules do not do this function. 

<h2>Bill of Materials</h2>

|Item|Quantity|price per unit|price total|
|----|-----|----|----|
|1s7p|60|$116.84| $7010.40|








