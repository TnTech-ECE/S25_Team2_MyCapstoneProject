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

- **T.3.3.3** – Operation of the BOTS to OFF must open the Shutdown Circuit (IC.9.2.2 / EV.7.2.2).  
- **T.4.2.5** – APPS implausibility > 100 ms → stop motor power (EV only).  
- **T.9.4.3** – Inertia switch (8–11 g) must open Shutdown Circuit.  
- **IC.9.1.1** – Shutdown Circuit components: Master Switch, Cockpit Switch, BSPD, BOTS, Inertia Switch.  
- **EV.5.6.3** – Discharge Circuit must be active whenever Shutdown Circuit is open, handle full system voltage for ≥ 15 s.  
- **EV.7.2.2** – When Shutdown Circuit opens, TS voltage must drop to LV (< 60 V) in ≤ 5 s.  

### 3.2 Technical Specifications

| Parameter                      | Value                                   |
| ------------------------------ | --------------------------------------- |
| **System Voltage**             | ~102 V DC                               |
| **Discharge Time Requirement** | ≤ 5 s                                   |
| **Max Residual Voltage**       | < 60 V DC                               |
| **Relay**                      | TE Connectivity Kilovac EV200AAANA<br>900 VDC / 500 A  |
| **Resistor**                   | uxcell 50 W, 400 Ω aluminum wirewound  |

### 3.3 Constraints

- **Regulatory**: Comply with FSAE EV4.10.x, EV5.6.3, EV7.2.2.  
- **Ethical/Safety**: ISO 6469-3 (EV shock protection).  
- **Economic**: Use COTS, cost-effective parts.  
- **Thermal**: Resistor must safely dissipate energy without exceeding 50 W rating.  

---

## 4. Overview of Proposed Solution

- **Components**:  
  - **Relay**: EV200AAANA (12 V coil)  
  - **Resistor**: 400 Ω, 50 W wirewound  
- **Operation**:  
  1. **Shutdown** → BMS drives relay coil  
  2. Relay closes → resistor across accumulator  
  3. Energy bleeds off → voltage falls  
  4. BMS monitors → opens relay when < 60 V  

---

## 5. Calculation for Capacitance

Given  
\(V(t)=V_0e^{-t/(RC)}\)  
and \(V(5)=60\), \(V_0=102\), \(R=400\,\Omega\):

\[
\begin{aligned}
60/102 &= e^{-5/(400C)}\\
\ln(60/102) &= -\frac{5}{400C}\\
C &= -\frac{5}{400\,\ln(60/102)} \approx 2.36\,\mathrm{mF}
\end{aligned}
\]

Any system capacitance ≤ 2.36 mF will discharge below 60 V in 5 s.

---

## 6. LTspice Simulation

*(Place your LTspice schematic file in `images/ltspice_schematic.png` and reference below)*


![CORRect](https://github.com/user-attachments/assets/f2303305-5583-453f-9f5a-b72c2d6f2b03)

---

## 7. Interface with Other Subsystems

- **Input**: 12 V “DISCHARGE” command from BMS  
- **Output**: HV accumulator terminals via AIR (–) relay  
- **Signal path**: BMS → relay coil → resistor → accumulator

---

## 8. 3D Model / Pictures of Components

*(Export your 3D renders or photos into `images/relay_3d.png` & `images/resistor_3d.png`)*

 ![Relay3D](https://github.com/user-attachments/assets/bc445f38-6993-4bbf-8e7b-8b1cfee02977)


![Resistors](https://github.com/user-attachments/assets/bc36e79f-05f0-4681-a6b8-2001444ad4f4)

---

## 9. Buildable Schematic

*(Include a clear schematic PDF or image in `images/buildable_schematic.png`)*
![Buildable-Schematic-Evan](https://github.com/user-attachments/assets/0c1f7f00-cfda-4b77-9ce8-c9f949435ac8)


![Discharge zoom](https://github.com/user-attachments/assets/94413c04-4771-41d9-af8c-e251bc0d16e4)

---

## 10. Circuit Design




![updated circuit](https://github.com/user-attachments/assets/f4a30d51-5470-4e1c-8b6a-1d3739c35933)

---

## 11. Flowchart


![flowchart 2](https://github.com/user-attachments/assets/cb4f59dd-7ed6-4f3c-a71e-ffcacdc681eb)


![flowchart](https://github.com/user-attachments/assets/1f065ce0-f329-403b-b729-c0abe62d7ff7)

---

## 12. Bill of Materials (BOM)

| Ref  | Component | Manufacturer / Series      | Part Number       | Distributor | Qty | Unit Price | Total   | Link                                                         |
| ---- | --------- | -------------------------- | ----------------- | ----------- | --- | ---------- | ------- | ------------------------------------------------------------ |
| R1   | Resistor  | uxcell                     | B07FDXPT9Y        | Amazon      | 1   | \$9.99     | \$9.99  | https://www.amazon.com/dp/B07FDXPT9Y                         |
| K1   | Relay     | TE Connectivity / Kilovac  | EV200AAANA        | Mouser      | 1   | \$145.88   | \$145.88| https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA |
| Q1   | Transistor| Onsemi TIP120              | TIP120G           | Mouser      | 1   | \$0.69     | \$0.69  | https://www.mouser.com/ProductDetail/onsemi/TIP120G          |
| D1   | Diode     | Onsemi 1N4004              | 1N4004RLG         | Mouser      | 1   | \$0.20     | \$0.20  | https://www.mouser.com/ProductDetail/onsemi/1N4004RLG        |

**Total Estimated Cost**: \$156.76

---

## 13. Analysis

- **Relay Selection**: EV200AAANA chosen for 900 VDC rating & 500 A capacity, automotive-grade.
-  ![data for relay](https://github.com/user-attachments/assets/8896e2c0-667f-407e-8b49-63776e5d9658)
- **Resistor Analysis**: \(P = V^2/R = 102^2/400 ≈ 26\) W < 50 W rating → 2× safety margin.  
- **Timing**: Calculated and simulated discharge meets < 5 s requirement.  
- **Reliability**: Simple, robust design with fail-safe BMS monitoring.


---

## 14. References

1. TE Connectivity, “EV200AAANA Contactor Datasheet,” 2024. [Online]. Available: https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA  
2. uxcell, “50W 400 Ω Aluminum Resistor Datasheet,” 2024. [Online]. Available: https://www.amazon.com/dp/B07FDXPT9Y  
3. SAE International, *2025 Formula SAE Electric Rules*, 2024. [Online]. Available: https://www
