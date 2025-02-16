## Experiment 1: Simulation and Design of CS Amplifier

### Aim
Simulate the DC analysis, Transient, and AC analysis of a CS amplifier circuit using LTSpice.
### Circuit
![circuit](https://github.com/user-attachments/assets/b31d8a43-07eb-42bc-8016-8dd0fb0644b7)

### Procedure

1. Design the CS amplifier circuit.
2. Naming the NMOS as CMOSN.
3. DC Analysis:Apply the DC voltage of  V<sub>DD</sub> = 1.8 V and V<sub>GS</sub> = 0.9 V . In LTSpice, go to the Simulate option and select Edit Simulation Command.Click on DC Analysis, then press OK.Click on Run in the tab menu to obtain the DC operating point V<sub>out</sub> .Set the Length as constant and determine the Width such that I<sub>D</sub> = 55.5 uA .

4. Transient Analysis:Modify the  V<sub>GS</sub> voltage source to a sine wave input with:
     - DC level= 0.9 V 
     - Amplitude= 50 mV 
     - Frequency= 1 kHz 
     \[In LTSpice, go to Edit Simulation Command, select Transient Analysis. Set the Stop Time as 5ms, then click OK.\]

5. AC Analysis:In Edit Simulation Command, select AC Analysis.Set the Type of Sweep to Decade.Set Points per Decade to 10.Set the Frequency Range from 0.1 Hz to 1 THz.Click OK. Determine the gain and frequency response of the circuit.

### Calculation

Power Calculation
 P = 100 uW

Drain Equation
V<sub>DD</sub> = V<sub>DS</sub> + I<sub>D</sub>*R<sub>D</sub> 

 P = I*V

Given: I<sub>D</sub> = 55.5 uA, V<sub>DD</sub> = 1.8 V 

Thus V<sub>DS</sub> = V<sub>out</sub> 

R<sub>d</sub>=32.4 Kohm ,but used 22 Kohm

Length= 180 nm

Width=18 um(found by varying the length).

V<sub>DS</sub>=0.467 V

Q point is (0.467 V,55.55 uA)

