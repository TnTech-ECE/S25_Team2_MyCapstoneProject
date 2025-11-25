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

Visual of experiment's procedure result:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/32c5ca8d-200f-4893-8ef5-515ea63edf58" />


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

    **Experiment 2:** 

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
