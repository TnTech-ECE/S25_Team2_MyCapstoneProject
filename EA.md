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

- **Purpose**:

  - Clearly state the exact criteria you intend to measure.
  - Criteria should align directly with your project's critical requirements or detailed design objectives.
  - Consider the customer's viewpoint: what features or performance attributes are most important from their perspective?
  - Anticipate that your instructor may require additional criteria for comprehensive evaluation.

- **Procedure**:

  - Provide detailed, step-by-step instructions outlining how the experiment will be conducted.
  - Include specifics such as required equipment, environmental conditions, and preparation steps.
  - Procedures should be detailed enough to ensure repeatability and clarity.
  - **Explicitly reference which items from your project inventory will be used in each step.**

- **Data Collection**:

  - Identify exactly what data will be recorded during the experiment.
  - Clearly specify units, methods of measurement, and formats for recording.
  - Include how frequently data points should be taken and how they will be documented (e.g., in tables, spreadsheets, video recordings).

- **Trials**:

  - Determine and justify how many repetitions of each experiment are necessary.
  - Multiple trials (e.g., N ≥ 3) are highly recommended to ensure statistical significance and reliability.
  - Consider using multiple copies or prototypes of your device to facilitate efficient testing and improve the robustness of your data.

- **Potential Biases**:

  - Identify potential sources of bias or errors that may impact experimental results.
  - Develop clear strategies to mitigate or control these biases (e.g., randomized trials, controlled environments, calibration of instruments).



## Conducting Experiments

All experiments were executed according to procedures above.

Data was logged using:

- Orion 2 BMS

Results/raw data were organized and logged into spreadsheets shown in section Analyzing Results.

Components used in each trial were recorded in the inventory log.

## Analyzing Results and Drawing Conclusions

After completing experiments:

- Thoroughly analyze all collected data, paying close attention to consistency and patterns.
- Evaluate your data to identify potential sources of error, bias, or abnormalities, and address their implications.
- Clearly articulate conclusions derived from the data, emphasizing evidence-based insights and interpretations.
- Identify correlations or suggest causal relationships, if supported by data.

If analysis uncovers questions or uncertainties, consider designing and executing additional targeted experiments to refine your understanding.

**Experiment 1 Results - Voltage Balance**


| Trial | Description | Maximum Voltage (V) on Leads| Maximum Voltage (V) on Leads| Components' Condition (New/Used) | Notes from each trial|  
|--------|-------------|----------|---------------|--------------|--------------|
|1| Readings from Orion BMS for voltage for each lead|3.46 V|3.45 V| Components were not damaged while conducting this experiment just opened from packaging to be used| The readings from the BMS show with time that the cell voltages on each lead will level out to be exactly equal|
|2| Voltage for each lead|3.45 V|3.45 V| Components were not damaged while conducting this experiment just opened from packaging to be used| The readings from the BMS show with time that the cell voltages on each lead will level out to be exactly equal|

**PASS** - Voltage readings level out within the timeframe or faster.

Visual tables from trial 1 using the Orion 2 BMS software:


<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/f46d3761-b67a-4852-8a82-a2a3d1e82fca" /> <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/624ff40d-b4c1-4627-8b57-d96013a28628" />



## Documenting and Tracking Components

Completed Inventory Table.
- **Initial Inventory**
  - List every item ordered, borrowed, or assigned.
  - Include vendor, order number, cost, and assigned storage location.

- **Usage Tracking**
  - For each experiment, identify which inventory items were used.
  - Record condition changes (e.g., damaged, consumed, modified).


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



## Writing the Report

Your deliverable should be a comprehensive markdown document, clearly organized, and uploaded to your project's GitHub repository.



For each documented experiment, you must include:

1. **Purpose and Justification**:

   - Explain why the experiment was designed, and how it relates to your critical success criteria.

2. **Detailed Procedure**:

   - Outline clearly the methods used, ensuring another team could reproduce your experiment.

3. **Expected Results**:

   - State your initial hypothesis or expectations clearly before conducting experiments.

4. **Actual Results**:

   - Present data collected during the experiments in an organized, easy-to-interpret format (tables, graphs, charts).

5. **Interpretation and Conclusions**:

   - Provide a detailed analysis explaining the significance of the results.
   - State whether results matched your expectations and explain any discrepancies.



When you have complete all of the experiments: clearly summarize whether your experiments demonstrated that your project meets the original success criteria outlined in your conceptual design. If success criteria were not met, discuss the reasons and outline steps for improvement. At the end of the report, include your **complete, updated component inventory table.**



## Statement of Contributions

Each team member must contribute meaningfully to the experimental analysis and document their contributions clearly in this section. Contributions should be recorded individually, and one team member may not document contributions on behalf of another. Each team member must clearly outline their involvement in experiment design, execution, data analysis, and reporting. By submitting this report, the team collectively certifies the accuracy and completeness of each member's stated contributions.

Mackenzie Raleigh

Marisol Miranda

Jordan Davis

Maddox Cagle
