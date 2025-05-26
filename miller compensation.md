 Design and Analysis of a Two-Stage CMOS Operational Transconductance Amplifier with Miller Compensation



## 1. Aim
To design and analyze a two-stage CMOS Operational Transconductance Amplifier (OTA) with Miller compensation for improved stability and phase margin.



## 2. Components/Software Required
- LTspice or equivalent SPICE-based simulator  
- CMOS Transistor Models  
- Power supply: 1.8V – 3.6V  
- Miller compensation capacitor (Cf)  
- Basic analog circuit elements (current mirrors, differential pairs)

## 3. Theory
Operational Transconductance Amplifiers (OTAs) are voltage-controlled current sources that are central to analog circuit design. Unlike conventional op-amps, OTAs are characterized by their transconductance  , defined as the ratio of output current to input voltage. They find widespread use in applications like active filters, analog multipliers, data converters, and phase-locked loops due to their high gain and linearity.

Two-Stage OTA Architecture
A two-stage OTA typically includes:

First Stage (Differential Amplifier): Provides high input impedance and initial voltage gain. It consists of a differential input pair (M1, M2) with an active load (current mirror formed by M3, M4). This stage converts the differential input signal into a single-ended voltage.

Second Stage (Gain Stage): A common-source amplifier (M5) with an active load (M6), which further amplifies the signal and drives the output.

Miller Compensation
To ensure stability in multi-stage amplifiers, frequency compensation is essential. In this design, Miller compensation is implemented by adding a capacitor between the output of the first stage and the output of the OTA.

This creates a dominant pole at the output of the first stage and splits the poles, pushing the non-dominant pole to a higher frequency.

As a result, it achieves a higher phase margin (typically > 60°), minimizing the risk of oscillation in feedback configurations.

However, it introduces a right-half-plane zero (RHPZ), which can degrade phase margin. Techniques like using a nulling resistor can help mitigate this issue.

Performance Trade-offs

High Gain: Achieved through cascoding or high-impedance loads.

Bandwidth vs. Stability: There's a trade-off between increasing unity-gain bandwidth and maintaining phase margin.

Power Efficiency: Controlled via the tail current source bias , allowing flexibility in low-power designs.

This design ensures robust performance across a wide supply voltage range (1.8V – 3.6V), making it suitable for modern low-power analog integrated circuits.


Target parameters:
- Supply Voltage: 1.8V – 3.6V  
- DC Gain: 50–70 dB  
- Unity Gain Bandwidth: Defined by gm/Cf  
- Phase Margin: > 60°  
- Power Efficiency: Optimized via Ibias



## 4. Circuit Diagram

![Picture1](https://github.com/user-attachments/assets/aadaa444-4f6e-43a0-b01e-adab77e56b2b)



## 5. Working Principle
A differential input at VIN+ and VIN− steers the tail current in M1 and M2. The current mirror reflects this to the second stage, where M5 amplifies the signal and M6 acts as load. Cf ensures stability by introducing a dominant pole and pushing non-dominant poles to higher frequencies.



## 6. Design Parameters
- **Supply Voltage:** 1.8 V to 3.6 V  
- **Transconductance (gm):** Dependent on Ibias  
- **DC Gain:** 50–70 dB  
- **UGBW:** Determined by gm/Cf  
- **Phase Margin:** > 60°  
- **Power Consumption:** Tuned by Ibias

## 7. Simulation Results

### 7.1 DC Operating Point
![Picture2](https://github.com/user-attachments/assets/9549737c-a683-4a61-bc38-fc68e0c7cbc4)

- Tail Current Source (I1): 10 μA  
- M1, M2 drain currents: ≈5.05 μA (balanced)  
- Common-source node (M5 drain): 1.251 V  
- Drain current of M6: 10.27 μA  
- Bias current M8: Matches expected topology  
- Gate currents: In pA to fA range  

### 7.2 Frequency Response
![Picture3](https://github.com/user-attachments/assets/96e562fa-aa26-45f4-a926-e812bfbc230f)

- Voltage Gain: ~54.01 dB (gain ≈501)  
- 3 dB Bandwidth: >43.19 kHz  
- Roll-off: −20 dB/decade  
- Phase Response: Indicates dominant pole beyond cutoff  


## 8. Applications
- Switched-capacitor filters  
- Analog signal processors  
- Sigma-Delta ADCs  
- Voltage-controlled oscillators  
- SoC amplifier blocks



## 9. Conclusion
The designed OTA achieves high gain, low power consumption, and excellent stability via Miller compensation. It suits precision analog front-ends. Future improvements may include simulation-based optimization using nulling resistors.



## 10. References
1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill, 2001  
2. P. R. Gray et al., *Analysis and Design of Analog Integrated Circuits*, Wiley, 2009  
3. Y. Tsividis and C. McAndrew, *Operation and Modeling of the MOS Transistor*, Oxford Univ. Press, 2011  
4. D. A. Johns and K. Martin, *Analog Integrated Circuit Design*, Wiley, 1997  
5. P. E. Allen and D. R. Holberg, *CMOS Analog Circuit Design*, Oxford Univ. Press, 2002  
