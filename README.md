## Experiment 1
### Design 1: Simulation of CS Amplifier
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
     
     In LTSpice, go to Edit Simulation Command, select Transient Analysis. Set the Stop Time as 5ms, then click OK.

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

Width=18 um(Found by keeping the Length constant).

V<sub>DS</sub>=0.467 V

Q point is (0.467 V,55.55 uA)

## Results:
1.**DC Analysis:**

![ccc](https://github.com/user-attachments/assets/e876cf20-3050-49e2-97ce-e13497734deb)

drain current I<sub>d</sub>=55.55 uA
V<sub>out</sub>=0.467 V \
Width=18 um for length=180 nm\

2.**Transient Analysis:**

![aaaa](https://github.com/user-attachments/assets/40f8bb2f-8759-454d-8be1-2b59453b4066)

There is 180 degree phase shift between input and output 

3.**AC Analysis:**
![fff](https://github.com/user-attachments/assets/9f6b82e7-6fb5-4289-8d5c-8d7b46b1a980)

Gain=20 dB

## Inference:
1.The Width of the MOSFET directly effects the Drain durrent.\
2.By changing the dimensions of the MOSFET we can directly control the amount of Drain current.\
3.180 degree phase shift between the input and output waveform.\
4.The CS amplifier has larger gain =20 dB.(ie, the ouput signal is 20 times larger then the input signal)\

### Design 2: Simulation of CMOS Amplifier
### Aim
Simulate the DC analysis, Transient, and AC analysis of a CMOS amplifier circuit using LTSpice.
### Circuit
![circ](https://github.com/user-attachments/assets/59ded92f-16cf-44d0-983b-fb3716183874)

### Procedure

1. Design the CMOS amplifier circuit.
2. Naming the NMOS as CMOSN and PMOS as CMOSP.
3. Apply the DC voltage of  V<sub>DD</sub> = 1.8 V
4. DC sweep Analysis: Go to the edit simulation command and select the DC sweep option and choose:
 -Source name= V<sub>in</sub>.
 -type of Sweep= Linear.
 -start value=0,
 -stop value =V<sub>DD</sub>=1.8 V.
 -increment=0.1.

find the V<sub>in</sub> from the vtc curve  
5. DC Analysis:put the appropriate V<sub>in</sub> value. go to the Simulate option and select Edit Simulation Command.Click on DC Analysis, then press OK.Click on Run in the tab menu to obtain the DC operating point V<sub>out</sub> .Set the Length as constant and determine the Width such that I<sub>D</sub> = 55.5 uA .

6. Transient Analysis:Modify the  V<sub>in</sub> voltage source to a sine wave input with:
     - DC level= 0.9 V 
     - Amplitude= 50 mV 
     - Frequency= 1 kHz 
     
     In LTSpice, go to Edit Simulation Command, select Transient Analysis. Set the Stop Time as 5ms, then click OK.
7. AC Analysis:In Edit Simulation Command, select AC Analysis.Set the Type of Sweep to Decade.Set Points per Decade to 10.Set the Frequency Range from 0.1 Hz to 1 THz.Click OK. Determine the gain and frequency response of the circuit.

### Calculation

 I<sub>D</sub> = 55.5 uA, V<sub>DD</sub> = 1.8 V 

Length M1= 180 nm\
Width=190 nm(found by keeping the Length of M1 constant)\
Length M2= 180 nm\
Width=449 um(found by keeping the Length of M2 constant)\

## Results:
1.**DC Sweep Analysis:**

![vtc](https://github.com/user-attachments/assets/bd151c9d-aa50-4c3e-851d-c51629390171)

 the value of the V<sub>in</sub> is selected as 0.8V as it is present in the middle of the saturation region of the VTC Curve.\
2.**DC Analysis:**

![v1](https://github.com/user-attachments/assets/f65f893b-9e5a-4ae8-a99b-b6141b5fa963)

drain current I<sub>d</sub>=55.55 uA
V<sub>out</sub>=1.22 V \
Length M1= 180 nm,Width=190 nm for M1.\
Length M2= 180 nm,Width=449 um for M2.\


3.**Transient Analysis:**

![v2](https://github.com/user-attachments/assets/47516b29-d33a-412a-bea1-5670ed20ea39)


There is 180 degree phase shift between input and output 

4.**AC Analysis:**

![v3](https://github.com/user-attachments/assets/87b38fa3-0122-4135-8281-e98faf89c8c1)


Gain=5.5 dB

## Inference:
1.The Width of the MOSFET directly effects the Drain durrent.\
2.By changing the dimensions of the MOSFET
 -M1 -when varying the width of PMOS there is not a lot of change in the drain current(ie, I<sub>D</sub> doesn't get effected much).\
 -M2 -when varying the width of NMOS there is drastic change in the drain current.\
3.If width is increased it leads to a higher gain.\
4.PMOS acts as a linear resistor.\
5.180 degree phase shift between the input and output waveform.\
6.The CMOS amplifier has gain =5.5 dB.(ie, the ouput signal is almost 6 times larger then the input signal)
