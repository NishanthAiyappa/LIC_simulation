##Experiment 1
Simulation and Design of CS Amplifier
#Aim
Simulate the DC analysis,Transient and AC analysis of a CS amplifier circuit using LT Spice.
#Procedure
1.Design the CS amplifier circuit.
2.Name the NMOS as CMOSN
DC Analysis: Apply the DC voltage of V_{DD}=1.8 V and V_{GS} = 0.9 V. Go to simulate option in the tab and edit simulation command, click on DC analysis and press ok. Click on Run in the tab menu to get the DC operating point ,Vout.Set the Length as constant and find Width such that the I_{d}=55.5 uA.
5.Transient Analysis: Change the V_{GS} voltage source to sine wave input of V_{gs}=0.9 V with an amplitude of 50 mV and frequency of 1 kHz by going to advanced menu,go to edit simulation command , click on transient analysis and give the stop time as 5 ms and click ok 
6.AC Analysis:  Similar to the above step go to the edit simulation command and click on AC analysis and change the time of sweep as decade , points=10 and frequency as .1 Hz to 1 THz and click on ok.Find the gain and frequency response of the circuit.
#Calculation
Power = 100 uW
Drain Equation: V_{dd}=V_{ds}+I_{d}*R_{d}
P=I*V (Id=55.55 uA , Vdd=1.8V)

clearly Vds=Vout; Vds>=Vgs-Vth
