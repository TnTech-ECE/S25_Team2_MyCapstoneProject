# Detailed Design Document: Discharge Circuit Subsystem

**Author**: Maddox Cagle  
**Team**: Capstone Team 2  

---

## 1. Function of the Subsystem

The discharge-circuit subsystem ensures the safe reduction of stored electrical energy in the Formula SAE Electric vehicle’s accumulator to below 60 V within 5 seconds, meeting regulatory requirements and ensuring team and public safety during shutdown or emergency conditions.

---

## 2. Integration within the Broader Solution

This subsystem integrates into the broader high-voltage safety and management system, interfacing directly with:

- **Battery Management System (BMS)**
- **Accumulator Isolation Relays (AIRs)**
- **Tractive System Master Switch (TSMS)**

Upon receiving a shutdown signal, the BMS engages the discharge relay to dissipate energy safely.

---

## 3. Specifications and Constraints

### 3.1 Rules Involving Shutdown & Discharge
Primary Rules:
- **T.3.3.3** – Operation of the BOTS to OFF must open the Shutdown Circuit (IC.9.2.2 / EV.7.2.2).  
- **T.4.2.5** – APPS implausibility > 100 ms → stop motor power (EV only).  
- **T.9.4.3** – Inertia switch (8–11 g) must open Shutdown Circuit.  
- **IC.9.1.1** – Shutdown Circuit components: Master Switch, Cockpit Switch, BSPD, BOTS, Inertia Switch.  
- **EV.5.6.3** – Discharge Circuit must be active whenever Shutdown Circuit is open, handle full system voltage for ≥ 15 s.  
- **EV.7.2.2** – When Shutdown Circuit opens, TS voltage must drop to LV (< 60 V) in ≤ 5 s.
  
All Rules for Shutdown, Precharge, and Discharge:

# Formula SAE Electric Rules – Shutdown, Precharge & Discharge Circuits

## Shutdown Circuit Rules (IC & T)

1. **T.3.3.3** – Operation of the Brake Overtravel Switch (BOTS) to the OFF position must open the Shutdown Circuit (IC.9.2.2 / EV.7.2.2).  
2. **T.4.2.5** – If an implausibility occurs between the values of the Accelerator Pedal Position Sensors (APPSs) and persists for >100 ms, power to the Electronic Throttle (IC) / Motor(s) (EV only) must be stopped completely. It is not necessary to open the Shutdown Circuit; the motor controller(s) stopping power is sufficient.  
3. **T.9.4.3** – Inertia Switch operation:  
   - Must trigger under a longitudinal impact deceleration of 8–11 g (per Sensata spec).  
   - Must open the Shutdown Circuit (IC.9.2.2) if triggered.  
   - Must latch until manually reset.  
   - May be reset by the driver from inside the driver’s cell.  
4. **IC.4.8.4** – When any of the above conditions exist, the Brake System Plausibility Device (BSPD) must open the Shutdown Circuit (IC.9.2.2).  
5. **IC.9.1** – Definition: Shutdown Circuit.  
6. **IC.9.1.1** – The Shutdown Circuit consists of:  
   1. Primary Master Switch (IC.9.3)  
   2. Cockpit Main Switch (IC.9.4)  
   3. (ETC only) Brake System Plausibility Device (BSPD) (IC.4.8)  
   4. Brake Overtravel Switch (BOTS) (T.3.3)  
   5. Inertia Switch (if used) (T.9.4)  
7. **IC.9.1.2** – Team must demonstrate all Shutdown Circuit features and functions at Technical Inspection.  
8. **IC.9.2** – Shutdown Circuit Operation.  
9. **IC.9.2.1** – Shutdown Circuit must open upon operation or detection from any component in IC.9.1.1.  
10. **IC.9.2.2** – When the Shutdown Circuit opens, it must:  
    - Stop the engine.  
    - Disconnect power to:  
      - Fuel pump(s)  
      - Ignition  
      - (ETC only) Electronic throttle (IC.4.1.1).  

## Additional Shutdown & Safety Rules

11. **EV.4.1.3** – If motors are mounted to suspension uprights, their cables and wiring must:  
    1. Include an Interlock (EV.7.8) that opens the Shutdown Circuit (EV.7.2.2) before wiring fails or the wheel/motor assembly is damaged.  
    2. Minimize length of wiring not meeting F.11.1.3.  
12. **EV.5.4.5** – A capacitor may hold the Isolation Relays (IRs) closed for up to 250 ms after the Shutdown Circuit opens (EV.7.2.2).  
13. **EV.5.5.3** – An Interlock (EV.7.8) must open the Shutdown Circuit (EV.7.2.2) when the Main Shutdown Device (MSD) is removed.  
14. **EV.5.6.1** – The accumulator must contain a Precharge Circuit that:  
    1. Charges the Intermediate Circuit to ≥ 90 % of accumulator voltage before closing the second IR.  
    2. Is supplied from the Shutdown Circuit (EV.7.1).  
15. **EV.5.6.3** – The Tractive System must contain a Discharge Circuit that:  
    1. Is always active when the Shutdown Circuit is open.  
    2. Discharges the Intermediate Circuit capacitors if the MSD has opened.  
    3. Is not fused.  
    4. Handles maximum Tractive System voltage for ≥ 15 s.  
16. **EV.6.6.5** – Battery packs with low-voltage or non-voltage-rated fusible links may be used if:  
    - An overcurrent device (≤ 1/3 the sum of parallel fusible links) compliant with EV.6.6.2.b is in series.  
    - BMS detects an open fusible link and opens the Shutdown Circuit (EV.7.2.2) on fault.  
    - Fusible link rating is specified by manufacturer or test data.  

##  Shutdown Circuit – Detailed EV7 Section

17. **EV.7.1** – Shutdown Circuit.  
18. **EV.7.1.1** – Components in series:  
    1. Battery Management System (BMS) (EV.7.3)  
    2. Insulation Monitoring Device (IMD) (EV.7.6)  
    3. Brake System Plausibility Device (BSPD) (EV.7.7)  
    4. Interlocks (as required) (EV.7.8)  
    5. Master Switches (GLVMS, TSMS) (EV.7.9)  
    6. Shutdown Buttons (EV.7.10)  
    7. Brake Overtravel Switch (BOTS) (T.3.3)  
    8. Inertia Switch (T.9.4)  
19. **EV.7.1.2** – Shutdown Circuit must carry current for IRs and Precharge Circuit relay.  
20. **EV.7.1.3** – BMS, IMD, and BSPD parts of Shutdown Circuit must be normally open.  
21. **EV.7.1.4** – BMS, IMD, and BSPD must have independent circuits to open the Shutdown Circuit; no single failure can feed power back.  
22. **EV.7.1.5** – Shutdown Buttons, BOTS, TSMS, GLVMS, and Interlocks must directly carry Shutdown Circuit current.  
23. **EV.7.1.6** – Team must demonstrate all Shutdown Circuit features/functions at Electrical Technical Inspection.  

## Shutdown Circuit Operation (EV.7.2)

24. **EV.7.2** – Shutdown Circuit Operation.  
25. **EV.7.2.1** – Shutdown Circuit must open when:  
    1. Any component in EV.7.1.1 operates or is detected.  
    2. Any shutdown of the GLV system.  
26. **EV.7.2.2** – When the Shutdown Circuit opens:  
    - The Tractive System must shutdown.  
    - All accumulator current flow must stop immediately (EV.5.4.3).  
    - Tractive System voltage must be low (< 60 V) within 5 s (T.9.1.2).  
    - Motors must spin free with no torque applied.  
27. **EV.7.2.3** – If BMS, IMD, or BSPD open the Shutdown Circuit:  
    1. Tractive System remains disabled until manual reset.  
    2. Reset only by manual action at the vehicle.  
    3. Driver cannot reactivate from inside the vehicle.  
    4. Shutdown Buttons or TSMS operation cannot close the Shutdown Circuit.  
28. **EV.7.2.4** – Cell balancing is not permitted when the Shutdown Circuit is open (EV.8.4).  
29. **EV.7.2.5** – If BMS detects a fault per EV.7.3.4, it must open the Shutdown Circuit (EV.7.2.2) and illuminate BMS & Tractive System status lights until manual reset.  
30. **EV.7.2.6** – If IMD detects a fault per EV.7.6.4, it must open the Shutdown Circuit (EV.7.2.2) and illuminate IMD & Tractive System status lights until manual reset.  

## Brake System Plausibility Device (BSPD) Rules (EV.7.7)

31. **EV.7.7.2** – BSPD must open the Shutdown Circuit (EV.7.2.2) when:  
    - Hard braking demand (EV.4.6).  
    - Motor/Accumulator current ≥ 5 kW at nominal battery voltage.  
    *BSPD may delay up to 0.5 s to prevent false trips.*  
32. **EV.7.7.3** – BSPD must open the Shutdown Circuit (EV.7.2.2) on any open/short in sensor input.  

## Interlock Rules (EV.7.8)

33. **EV.7.8.3** – An Interlock must:  
    - Open the Shutdown Circuit (EV.7.2.2) if connection is broken.  
    - Not be in the low (ground) return for IR coils.  

## Tractive System Master Switch (TSMS) (EV.7.9)

34. **EV.7.9.3** – TSMS must:  
    1. Open the Shutdown Circuit (EV.7.2.2) in OFF position.  
    2. Be last switch before IRs (excluding Precharge/Interlocks).  
    3. Be centered in a ≥ 50 mm orange circle.  
    4. Be labeled “TS” with ISO 7010-W012 symbol.  
    5. Have lockout/tagout capability in OFF.  

## Shutdown Buttons (EV.7.10)

35. **EV.7.10.2** – Each Shutdown Button must:  
    1. Be a push-pull or push-rotate emergency stop switch.  
    2. Open the Shutdown Circuit (EV.7.2.2) when moved OFF.  
    3. Hold open until manually reset.  
    4. Close the Shutdown Circuit when moved ON.  

## Charging Shutdown Circuit (EV.8)

36. **EV.8.1.1** – Charger & Charging Shutdown Circuit features/functions must be demonstrated at Electrical Technical Inspection.  
37. **EV.8.2.7** – Charger Shutdown Button must:  
    1. Be push-pull or push-rotate, ≥ 25 mm diameter.  
    2. Open the Charging Shutdown Circuit (EV.8.4.2) when OFF.  
    3. Hold OFF until manual reset.  
    4. Be labeled with the standard emergency symbol.  
38. **EV.8.3.1** – Charging Shutdown Circuit consists of:  
    1. Charger Shutdown Button (EV.8.2.7)  
    2. BMS (EV.7.3)  
    3. IMD (EV.7.6)  
39. **EV.8.3.2** – BMS and IMD parts of Charging Shutdown Circuit must be normally open and have independent circuits to prevent back-feed.  
40. **EV.8.4.1** – During charging, BMS & IMD must monitor accumulator and open Charging Shutdown Circuit on fault.  
41. **EV.8.4.2** – When Charging Shutdown Circuit opens:  
    - All charging current stops immediately.  
    - Tractive System voltage ≤ 60 V within 5 s (T.9.1.2).  
    - Charger turns off and remains disabled until manual reset.  

## Low Voltage & System Activation (EV.9)

42. **EV.9.3** – Low-Voltage (GLV) System may be active when Shutdown Circuit is closed.  
43. **EV.9.4.2** – Tractive System Active only possible when:  
    1. GLV System is energized.  
    2. Shutdown Circuit is closed.  

## Precharge & Discharge Circuit Summary (EV.5.6)

44. **EV.5.6** – Precharge and Discharge Circuits.  
45. **EV.5.6.3** – Discharge Circuit must:  
    1. Be active whenever Shutdown Circuit is open.  
    2. Discharge Intermediate Circuit capacitors if MSD is open.  
    3. Not be fused.  
    4. Handle maximum Tractive System voltage for ≥ 15 s.  
46. **EV.5.6.4** – PTC devices must not limit current for Precharge or Discharge Circuits.  
47. **EV.6.5.4** – GLV systems (except IRs, parts of Precharge/Discharge, HV DC/DC, BMS, IMD, Ready-to-Move light, Energy Meter, cooling fans) must not be inside the accumulator container.  


### 3.2 Technical Specifications
Connections:
Pin 24 will be used for the inputs and output to the Orion 2 BMS.
Summary of Specifications:
| Parameter                      | Value                                   |
| ------------------------------ | --------------------------------------- |
| **System Voltage**             | ~102 V DC                               |
| **Discharge Time Requirement** | ≤ 5 s                                   |
| **Max Residual Voltage**       | < 60 V DC                               |
| **Relay**                      | TE Connectivity Kilovac EV200AAANA<br>900 VDC / 500 A  |
| **Resistor**                   | uxcell 50 W, 400 Ω aluminum wirewound  |
### Relay Specifications in Detail
![1](https://github.com/user-attachments/assets/67b4f942-459e-4fb6-b445-4a3119fa2648)

![2](https://github.com/user-attachments/assets/98d6b19c-c505-4ef4-862f-4cd975299d82)

### Resistor Specifications in Detail

**uxcell 50 W 400 Ω Aluminum Wirewound Resistor** [2]

- **Power & Resistance**: 50 W, 400 Ω, 5 % tolerance. Wire-wound construction provides high stability and accuracy across a wide resistance range.  
- **Housing**: Aluminum case with an insulated cover suppresses heat and ensures reliable thermal performance.  
- **Materials & Overload Capability**: Built from qualified copper, nickel, and aluminum; compact structure and heat-dissipation design allow for built-in overload handling.  
- **Mechanical Dimensions**: Board length 1.96 in (49.8 mm) with two 3.5 mm mounting holes and two terminals for connection.  
- **Reliability & Applications**: Suitable for AC/DC circuits, converters, inverters, motor‐speed control, driver circuits, and other high-power applications.  

### 3.3 Constraints

- **Regulatory**: Comply with FSAE EV4.10.x, EV5.6.3, EV7.2.2. [3]
- **Ethical/Safety**: ISO 6469-3 (EV shock protection). [4] 
- **Economic**: Use COTS, cost-effective parts. [1][2]
- **Thermal**: Resistor must safely dissipate energy without exceeding 50 W rating. [3]  

---

## 4. Overview of Proposed Solution
The discharge circuit consists of the EV200AAANA relay and a 400 Ω resistor. If the shutdown circuit becomes active, the BMS signals the relay coil, closing contacts and connecting the resistor across the accumulator terminals. The resistor rapidly dissipates stored energy in the capacitors, safely reducing voltage to below 60 V within the mandated 5 seconds. This is according to rule EV.7.2.2. [3]
- **Components**:  
  - **Relay**: EV200AAANA (12 V coil)  
  - **Resistor**: 400 Ω, 50 W wirewound  
- **Operation**:  
  1. Shutdown → BMS drives relay coil  
  2. Relay closes → resistor across accumulator  
  3. Energy bleeds off → voltage falls  
  4. BMS monitors → opens relay when < 60 V  

---

## 5. Calculation for Capacitance

Voltage across the capacitor over time:
V(t) = V0 x e^(-t/RC)
Where:
	V is the initial voltage (e.g., 102 V)
	R is the resistance (400 Ω)
	C is the capacitance of the system
	t is the time in seconds
To find the required capacitance that would allow the voltage to drop below 60 V in 5 seconds:[3]
60 = 102 x e^(-5/(400*C))
C = - 5/(400*ln⁡(60/102))
C = 0.002355569817 F

Any system capacitance ≤ 2.356 mF will discharge below 60 V in 5 s.

---

## 6. LTspice Simulation



![CORRect](https://github.com/user-attachments/assets/f2303305-5583-453f-9f5a-b72c2d6f2b03)

---

## 7. Interface with Other Subsystems

- **Input**: 12 V “DISCHARGE” command from BMS  
- **Output**: HV accumulator terminals via AIR (–) relay  
- **Signal path**: BMS → relay coil → resistor → accumulator
- **Connections**: Communication connection = pin 12 on Orion BMS
  	           Power terminals: N = None C = Molex-fit Jr, 2 Skt, Female 18-24, P/N 39-01-2020 & 39-00-0060 +red is pin 1 (A length only)
---				    A = Bottom Mount & Male 10 mm x M8 Terminals

## 8. 3D Model / Pictures of Components (Relay on left and Resistor on right)

 ![Relay3D](https://github.com/user-attachments/assets/bc445f38-6993-4bbf-8e7b-8b1cfee02977)
![Resistors](https://github.com/user-attachments/assets/bc36e79f-05f0-4681-a6b8-2001444ad4f4)

---

## 9. Buildable Schematic

![Buildable-Schematic-Evan](https://github.com/user-attachments/assets/0c1f7f00-cfda-4b77-9ce8-c9f949435ac8)


![Discharge zoom](https://github.com/user-attachments/assets/94413c04-4771-41d9-af8c-e251bc0d16e4)

---

## 10. Circuit Design




![updated circuit](https://github.com/user-attachments/assets/f4a30d51-5470-4e1c-8b6a-1d3739c35933)

---

## 11. Flowcharts


![flowchart 2](https://github.com/user-attachments/assets/cb4f59dd-7ed6-4f3c-a71e-ffcacdc681eb)


![flowchart](https://github.com/user-attachments/assets/1f065ce0-f329-403b-b729-c0abe62d7ff7)

---

## 12. Bill of Materials (BOM)

| Ref  | Component | Manufacturer / Series      | Part Number       | Distributor | Qty | Unit Price | Total   | Link                                                         |
| ---- | --------- | -------------------------- | ----------------- | ----------- | --- | ---------- | ------- | ------------------------------------------------------------ |
| R1   | Resistor  | uxcell                     | B07FDXPT9Y        | Amazon      | 1   | \$9.99     | \$9.99  | https://www.amazon.com/dp/B07FDXPT9Y                         |
| K1   | Relay     | TE Connectivity / Kilovac  | EV200AAANA        | Mouser      | 4   | \$191.72   | \$766.88| https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA |


**Total Estimated Cost**: \$776.87

---

## 13. Analysis

- **Relay Selection**: EV200AAANA chosen for 900 VDC rating & 500 A capacity, automotive-grade.
  
  ![data for relay](https://github.com/user-attachments/assets/8896e2c0-667f-407e-8b49-63776e5d9658)
- **Resistor Analysis**: P = V^2/R = 102^2/400 ≈ 26 W < 50 W rating → 2× safety margin.  
- **Timing**: Calculated and simulated discharge meets < 5 s requirement.  
- **Reliability**: Simple, robust design with fail-safe BMS monitoring.


---

## 14. References

[1] TE Connectivity, “EV200AAANA Contactor Datasheet,” 2024. [Online]. Available: https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA  

[2] uxcell, “50W 400 Ω Aluminum Resistor Datasheet,” 2024. [Online]. Available: https://www.amazon.com/dp/B07FDXPT9Y  

[3] SAE International, *2025 Formula SAE Electric Rules*, 2024. [Online]. Available: https://www.fsaeonline.com

[4] International Organization for Standardization, "ISO 6469-3:2021 Safety specifications for electrically propelled vehicles," ISO, 2021.   

[5] GitHub, “Reports/Detailed Design Files/Detailed Design - Evan Morse.md,” GitHub, 2025. [Online]. Available: https://github.com/northsack/F24_Team2_FormulaSAE/blob/Evan-Morse--DD/Documentation/Images/Buildable-Schematic-Evan.PNG    

