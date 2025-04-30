<h1> Detailed Design: Sensors and Battery Cells </h1>
The Formula SAE vehicle requires a battery similar to the Zero Motor's battery in electrical characteristics in order to function properly. Namely, the output voltage should be 102 volts with a nominal energy capacity of 6.3 kwh.
*Formula SAE has a number of rules regarding the battery cells and sensors, namely: 
--
*additionally we would like, 
--Keep the dimensions similar to the Zero Motor's battery -- this may not be possible.

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
We want to use the Samsung SDI 50S batteries in a 28 cell in series to 12 cells in parralel configuration to reach the electrical characteristics of the Zero Motor's battery. 
For the sensors we have options: enepaq sells some battery packs. 
Additionally, enepaq's batteries that they sell are also not listed with their prices on their vendors.

enepaq would be a great source for the sensors and insulation for the batteries, they supply thier battery packs through digikey. The packs configure the cells into a paralel configuration so we will need 56 1s6p or 28 2s6p for a total cost of 
They may not have a size that fits for the Samsung S50 battery, so we may have to chose a different battery cell.
