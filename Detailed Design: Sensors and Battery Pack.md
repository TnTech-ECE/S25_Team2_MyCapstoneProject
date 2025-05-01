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
We want to use the BL5000C21703S3PFTM106ICC1NN from GlobTek, Inc battery packs in a 10 cell in series to 4 cells in parralel configuration to reach the electrical characteristics of the Zero Motor's battery. 
The battery packs contain sensors however they communicate on SMbuss lines. The appropriate protocols will have to be applied in the BMS.

