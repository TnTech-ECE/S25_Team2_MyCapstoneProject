 # FSAE Electric Accumulator System Experimental Analysis 

This Experimental Analysis documents a test campaign to assess the Formula SAE Electric accumulator system for its critical safety, performance, and compliance requirements. The accumulator was built as a 6s12p pack using Samsung 21700-50S cells, assembled with nickel strip, and controlled by an Orion O2 Battery Management System with a Thermistor Expansion Module for temperature monitoring.

All experiments were designed to verify:
1. **Safety** (thermal stability, isolation, fault protection)
2. **Electrical performance**
3. **BMS functionality**
4. **Compliance with 2025 FSAE Electric rules**

This document includes experiment design, data collection, analysis, conclusions, and a complete component inventory.

## Designing Experiments

The purpose of the experiments are designed to verify safety, performance, efficiency, and compliance with Formula SAE standards.

   **Experiment 1:** Cell Voltage Verification and Pack Balancing

Evaluate whether the 6s12p module maintains proper cell voltage uniformity and whether the Orion O2 BMS can detect imbalance and execute passive balancing with time.

Critical Requirements:

- Voltage through pack is roughly 3.45 V
- BMS conducts the voltage and shows balance throughout time
- Thermistors must detect changes within ±2°C accuracy
- Compliancce with FSAE rule (if there is a rule place here)

Procedure:

1. Assemble a 6s12p module using 72 Samsung 21700-50S cells..
2. Connected leads for Orion 2 BMS for one pack with pins 1-5 on different leads and 6-12 on one lead.
3. Placed Fuses on in approiate and rule regulated ends of battery segements.
4. Place thermistors evenly across cell groups (8 total).
5. Logged voltage and temperature at start.
6. Allow the battery to rest for 30 minutes.
7. Logged voltage and temperature after the 30 minutes.
8. Trigger a balancing cycle in the Orion BMS and record:

   - Initial voltages
   - Balancing activation status
   - Final voltages

Data Collection:

* Voltage per lead (V)
* Pack voltage (V)
* Temperature of groups during balancing (°C)

Trial(s):

N=2 (sufficient for statistical reliability)

Potential Bias:

1. Wiring fault -> mitigated soldering and spot welding to ensure connection.
2. Bad battery cell -> measure each cell before connection.
3. Meter calibration differences -> mitigated by using one multimeter for all readings as well as the BMS to confirm.

**Experiment 2:** Low-Current Load Test
   
Evaluate whether the 6s12p module maintains stable voltage and minimal thermal rise under a controlled low-current discharge. This experiment also provides a baseline estimate of internal resistance.

Critical Requirements:

 - Load current remains approximately 2.2 A
 - Voltage sag is smooth without sudden drops
 - Temperature increase stays below 3 °C
 - Safe connections with no arcing or loose terminals
 - Compliance with FSAE accumulator testing safety guidelines

Procedure:

  1. Confirm 6s12p module integrity and inspect all connections.
  2. Attach a 10 Ω / 200 W resistor across pack terminals using insulated wiring.
  3. Measure open-circuit voltage with a DMM.
  4. Apply the load and begin timing the 180-second test period.
  5. Record voltage and temperature at 0, 60, 120, and 180 seconds.
  6. Remove load and record recovered open-circuit voltage.
  7. Calculate internal resistance using ΔV / I.

Data Collection:
 - Voltage under load (V)
 - Current (A)
 - Module surface temperature (°C)
 - Estimated internal resistance (Ω)

Trial(s):

N = 2

Potential Bias:
 1. Heating of leads: mitigated by using 14 AWG silicone wire.
 2. Resistor tolerance: minimized by using a high-power resistor rated ±5 %.
 3. Meter error: mitigated by using a single calibrated DMM across all readings.

**Experiment 3:** Medium-Low Load Stability Test
   
Evaluate module stability under a moderate 5 A constant-current discharge and confirm that temperature rise and voltage drop behave smoothly.

Critical Requirements:

 - Constant-current operation at 5.00 A ± 0.05 A
 - Voltage should decline steadily without step-change drops
 - Temperature rise remains under 5 °C
 - Electronic load and wiring rated for ≥10 A

Procedure:

 1. Connect the 6s12p module to a programmable DC electronic load.
 2. Configure load to CC mode at 5.00 A, cutoff voltage 18 V.
 3. Record voltage and temperature at 0, 60, 120, and 180 seconds.
 4. Disable load and record stabilized voltage after 2 minutes.

Data Collection:
 - Voltage versus time (V)
 - Temperature versus time (°C)
 - Regulated discharge current (A)

Trial(s):

N = 2

Potential Bias:

 1. Electronic load calibration drift → mitigated by validating current with DMM.
 2. Temperature measurement lag → minimized by placing thermistor directly on cell can.
 3. Connector resistance → mitigated via bolted lugs rather than clip leads.

**Experiment 4:** I–V Curve Characterization
   
Assess the relationship between module voltage and current at two discharge points to approximate pack behavior and identify potential weak cells or excessive resistance.

Critical Requirements:

 - Voltage reading accuracy ±10 mV
 - Stable current at each measurement point
 - Two reliable load points (≈2.2 A and 5 A)
 - Safe operation at all times

Procedure:

 1. Use data from Experiments 2 and 3 to obtain voltage at two load levels.
 2. Document voltage values at:
      - 2.21 A
      - 5.00 A
 3. Plot voltage versus current to obtain an approximate I–V relationship.
 4. Evaluate curve slope for health indicators.

Data Collection:
 - Current (A)
 - Voltage at each load point (V)
 - Approximate slope (ΔV/ΔI)

Trial(s):

N = 2

Potential Bias:

 1. Temperature drift between tests: minimized by performing tests consecutively.
 2. Variation in electrical contact: mitigated using the same lugs and wires in both tests.
 3. Meter variance: mitigated by using the same DMM for voltage readings.

**Experiment 5:** Low-Current Charging Test
   
Determine whether the module charges normally at a low current, and monitor temperature, voltage rise, and BMS observations.

Critical Requirements:

 - Charge current remains at 3.00 A ± 0.05 A
 - Final voltage does not exceed 25.2 V
 - Temperature rise ≤3 °C
 - Charger must be in CC/CV mode

Procedure:

 1. Configure a bench charger to 3 A and max voltage 25.2 V.
 2. Connect charger to pack using proper polarity.
 3. Log voltage and temperature at 0, 5, and 10 minutes.
 4. Monitor BMS for charging behavior and potential OV warnings.\
 5. Disconnect charger and verify stable resting voltage.

Data Collection:
 - Pack voltage (V)
 - Temperature (°C)
 - Charging current (A)

Trial(s):

N = 2

Potential Bias:

 1. Charger calibration drift: mitigated by verifying current with DMM.
 2. Incomplete thermal contact: minimized using taped thermistor on cell casing.
 3. Ambient temperature variation: mitigated by conducting all tests indoors.

**Experiment 6:** BMS Monitoring and Fault Response Simulation
   
Verify Orion O2 BMS functionality including voltage sensing, temperature sensing, and detection of simulated faults such as overvoltage, missing sensors, and sense-wire failure.

Critical Requirements:

 - BMS must detect OV/UV conditions correctly
 - Temp sensors must be within ±2 °C accuracy
 - Sense-wire faults must open the shutdown circuit
 - BMS fault indicators must latch until reset
 - Compliance with FSAE EV.7.x BMS monitoring requirements

Procedure:

 1. Power Orion O2 BMS using a GLV supply (not the pack).
 2. Connect pack sense harness to BMS.
 3. Record baseline cell voltages, pack voltage, and temperatures.
 4. Simulate faults:
    - Overvoltage event (software simulation)
    - Removal of a temperature sensor
    - Disconnection of a sense lead
 5. Observe and record:
    - Fault flag
    - Shutdown signal behavior
    - Indicator light activation

Data Collection:

 - Cell voltages (V)
 - Pack voltage (V)
 - Temperature readings (°C)
 - Fault logs and shutdown responses

Trial(s):

N = 2

Potential Bias:

 1. Loose connectors: mitigated with strain-relief and locking connectors.
 2. GLV noise: reduced by filtering and stable power supply.
 3. Human error during fault simulation: mitigated by documenting each step before execution.
    
## Conducting Experiments

All experiments were executed according to procedures above.

Data was logged using:

- Orion 2 BMS

Results/raw data were organized and logged into spreadsheets shown in section Analyzing Results.

Components used in each trial were recorded in the inventory log.

## Analyzing Results and Drawing Conclusions

Collected data from all the experiments were analyzed, after which consistent trends were identified, possible sources of error or bias evaluated, and whether or not the system was behaving as expected was determined. Results will be used to make clearly defined, evidence-based conclusions and explore possible correlations and/or cause-and-effect relationships in the variables that were measured. Any uncertainties or unexpected findings were noted as areas for potential follow-up testing to further refine the understanding and validation of the system.

**Experiment 1 Results - Voltage Balance**


| Trial | Description | Maximum Voltage (V) on Leads| Minimum Voltage (V) on Leads| Components' Condition (New/Used) | Notes from each trial|  
|--------|-------------|----------|---------------|--------------|--------------|
|1| Readings from Orion BMS for voltage for each lead|3.46 V|3.45 V| Components were not damaged while conducting this experiment just opened from packaging to be used| The readings from the BMS show with time that the cell voltages on each lead will level out to be exactly equal|
|2| Voltage for each lead|3.45 V|3.45 V| Components were not damaged while conducting this experiment just opened from packaging to be used| The readings from the BMS show with time that the cell voltages on each lead will level out to be exactly equal|

**PASS** - Voltage readings level out within the timeframe or faster.

Visual tables from trial 1 using the Orion 2 BMS software:


<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/f46d3761-b67a-4852-8a82-a2a3d1e82fca" /> <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/624ff40d-b4c1-4627-8b57-d96013a28628" />

The results from this experiment prove that the Orion O2 BMS will correctly measure and report the voltage levels of a given cell group, but only after a brief stabilization period has passed since its connection or power-up. Immediately after pack energizing, the BMS takes a number of seconds to poll each of the sense lines, verify signal integrity, and execute its internal filtering and averaging routines. During this time, minor variations in the displayed voltage values were noticed, but the deviations also consistently converged toward stable, precise readings within the expected time window.

## Documenting and Tracking Components

Completed Inventory Table.

| Item # | Description | Quantity | Vendor/Source | Order # / ID | Storage Location (Lab Station / Box #) | Date Acquired | Condition (New/Used) | Notes (Experiment Used, Damaged, Returned) |  
|--------|-------------|----------|---------------|--------------|-----------------------------------------|---------------|----------------------|--------------------------------------------|
|--------| Samsung 21700 50s|377|Samsung|--------------|AIEB 181|August 2025|New|72 cells have been used for testing, there is still 305 can be used|
|--------|Orion 2 BMS|1|Evolve Electronics|--------------|AIEB 181|August 2025|New|Being used for experiments|
|--------| Orion 2 BMS Thermistor Expansion Module |1|Evolve Electronics|--------------|AIEB 181|August 2025|New|Being used for experiments|
|--------|Relays|6|TE Connectivity|--------------|AIEB 181|August 2025|New|--------------------------------------------|
|--------|Jrready ST6359 Deutsch Connector Kit|1|McMaster-Carr|--------------|AIEB 181|August 2025|New|Being used for experiments|
|--------| Wire Assortments |1|McMaster-Carr|--------------|AIEB 181|August 2025|New|--------------------------------------------|
|--------| Battery Blanket|3|McMaster-Carr|--------------|AIEB 181|August 2025|New|--------------------------------------------|
|--------| ISOMETER IR155 3204 (IMD)|1|Onrion|--------------|AIEB 181|August 2025|New|--------------------------------------------|
|--------| Fuse 350A/32V Pack of 4|3|PlusRoc|--------------|AIEB 181|August 2025|New|6 fuses have been used for experiments, there are 6 left to be used|
|--------| Fuse Holders|6|Victron Energy|--------------|AIEB 181|August 2025|New|--------------------------------------------|
|--------| Nickel alloy strip|2|Bestol|--------------|AIEB 181|August 2025|New|Used for connecting the cells in the 6s12p configuration|
|--------| Battery Holder Bracket cell|6|Bestol|--------------|AIEB 181|August 2025|New|Used to hold cells in the configuration created|




## Statement of Contributions

Mackenzie Raleigh

* Co-wrote Experimental Analysis
* Help create experiments to test

Marisol Miranda

* Co-wrote Experimental Analysis
* Dealt with the Orion 2 BMS software and installation

Jordan Davis

* Co-wrote Experimental Analysis
* Designed and built battery cell segements

Maddox Cagle

* Co-wrote Experimental Analysis
