
### **Differential Amplifier**
## **Aim:**

Design and analyze the MOS differential amplifier circuit for the given specifications:

- V<sub>DD</sub>=3.3 V
- p<=3 mW
- V<sub>ICM</sub>=1.65 V
- V<sub>ocm</sub>=1.7 V
- V<sub>P</sub>=0.5 V

## Theory

A differential amplifier is a key circuit in analog electronics that amplifies the difference between two input signals while rejecting common-mode signals (noise). It is widely used in operational amplifiers (op-amps), instrumentation amplifiers, and analog circuits.
A basic MOSFET differential amplifier consists of:

Two matched MOSFETs (M1 and M2) forming a differential pair

A current source I<sub>SS</sub> as a tail current

Two drain resistors R<sub>D</sub>

When the inputs V<sub>in1</sub> and V<sub>in2</sub> are equal, the circuit is balanced, and the current splits equally.

When V<sub>in1</sub> increases while V<sub>in2</sub> decreases, M1 conducts more current, and M2 conducts less, creating a voltage difference at the outputs.

The circuit rejects common-mode signals (same voltage at both inputs) and only amplifies the differential component


**Circuit 1** <br>
**design Rd and Rss**

![image](https://github.com/user-attachments/assets/6caf6b0a-5821-4259-8b8d-80fce68f4cb9)

ss  and stability of the circuit.
- **NMOS Transistors (M1 and M2):** Act as the main amplifying elements, forming a differential pair that amplifies the difference between the two input signals.
- **Output Nodes (V<sub>OCM</sub> and V<sub>2OCM</sub>):** The differential output signals are taken from these points.

Calculation:
![image](https://github.com/user-attachments/assets/f7a39423-0de0-439c-b98a-217d4620e004)

from the calculation we have found I<sub>SS</sub> value as 0.909 mA <br>
I<sub>D1</sub> and I<sub>D2</sub> as 0.45 mA <br>
R<sub>D</sub> as 2.5 kohm <br>
R<sub>SS</sub> as 550 ohm <br>
V<sub>GS</sub>=V<sub>G</sub> - V<sub>p</sub> = 1.65 V - 0.5 V = 1.15 v <br>
V<sub>OV</sub> = V<sub>GS</sub> - V<sub>th</sub> = 1.15 V - 0.366 V = 0.784 V <br>


### **DC Analysis**

1. **Open LTspice XVII** and load the MOS differential amplifier circuit schematic.
2. **Set Up the Simulation Command:**
   - Click on **Simulate** > **Edit Simulation Cmd**.
   - In the **DC op pnt** tab, select **.op (DC Operating Point Analysis)**.
   - Click **OK**, and place the generated command on the schematic.
3. **Check the Component Parameters:**
   - Ensure that the MOSFET models and resistor values match the given specifications.
   - Verify that the power supply voltages (Vdd, Vicm) are correctly set.
4. **Run the Simulation:**
   - Click on **Run**.
   - 
![image](https://github.com/user-attachments/assets/11c557c2-3210-4b50-9a06-5f3bd5e15e0d)


to set correct operating point ,the width and length values are
width = 208 u <br>
length = 6 u <br>


### **Analysis**

### Effect of VICM on Vout and Id
Vicm is varried from 0 to 3.3 V.

Variation in Vocm

![VaryingVicm_vout](https://github.com/user-attachments/assets/72524952-5d99-4425-818a-b55914852ad3)


Variation in Id

![VaryingVicm_id](https://github.com/user-attachments/assets/2e6f4518-96d6-4e89-b2b0-daab045ad882)

| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Drain Current  (Id)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.65V**                            | **1.70V**             | **0.45 mA**                |
| **1.3V**                            | **2.32V**                 | **0.26 mA**               |



As the common-mode input voltage \( VICM \) increases, the drain current also increases, causing a shift in the operating point, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).

### **Calculate Gain**

![image](https://github.com/user-attachments/assets/fd9ae479-071b-4594-b645-595a6984d270)


### **Calculate maximum input and output Swing**

![d347429a-45cd-4393-940e-c9ef2ae17f5b](https://github.com/user-attachments/assets/4c0f610f-6737-4329-b9ae-218b31ba7b20)



### **TRANSIENT ANALYSIS**
1.go to configure Analysis and select transient analysis then <br>
2.stop time as 1m ,time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• DC Offset: 1.65 V
• Amplitude: 25 mV
• Frequency: 1 kHz

3.put the same values for V2 but change the phase angle.

4.And in V2 phi(deg) as 180

![image](https://github.com/user-attachments/assets/56a19522-3e12-4eb1-90e6-1f690d6d9447)
 The Gain is 3.02.

when the input voltage is more then the minimum swing or outside the allowable swing the output wave form deforms, ie it is in triode or cutoff region.


![trans1](https://github.com/user-attachments/assets/161df988-2108-4ca1-a5c4-7ab6cca6d8b7)


### **AC Analysis**
• Type of sweep: Decade
• Number of points per decade: 10
• Start frequency: 0.1 Hz
• Stop frequency: 1 THz
AC Amplitude as 1 and AC Phase as 0 in V1 <br>
AC Amplitude as 1 and AC Phase as 180 in V2 <br>

![Screenshot 2025-03-02 220006](https://github.com/user-attachments/assets/ecfef7ef-22da-4aa5-93b4-74fba38dd18f)

## Variation of Gain wrt to  different Vicm.

- the Vout remains almost unchanged when both the Vicm is varied simultaneously, if the Vicm voltages is varied at different directions the Vout changes from each other,if the input signal of the second MOSFET is increased its gain reduces.

  V2(50 mV) is given a different input signal than the V1(25 mV).
  
![image](https://github.com/user-attachments/assets/c84dcad9-74ae-4924-a6a5-2f71606bfc54)

### **Circuit 2** <br>

Replace the resistor with a current source=0.909mA. 
![image](https://github.com/user-attachments/assets/9c695010-58d1-4483-8dce-6e54354695c9)

### **DC Analysis**
![image](https://github.com/user-attachments/assets/dfaa102d-a894-4d6a-8957-a3e214736714)

### Effect of VICM on Vout and Id
Vicm is varried from 0 to 3.3 V.

Variation in Vocm

![image](https://github.com/user-attachments/assets/7f9c4dcd-0fd1-4817-9a8a-8fe0155e1047)


Variation in Id

![image](https://github.com/user-attachments/assets/4b839f99-6be4-4a80-b9c9-7074b9971699)

| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Drain Current  (Id)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.65V**                            | **1.71V**             | **0.46 mA**                |
| **1.3V**                            | **2.1V**                 | **0.32 mA**               |



### **TRANSEINT ANALYSIS**
![image](https://github.com/user-attachments/assets/841008c0-9d37-41aa-a072-934c0a4ac0bc)

if Vin is more then the allowable swing.

![image](https://github.com/user-attachments/assets/76994ebf-9b99-417a-b7ad-6c28a5e40cfb)

### **AC ANALYSIS**

![Screenshot 2025-03-02 223315](https://github.com/user-attachments/assets/d0db6eb8-ab1e-4649-bf22-f65bace10bb8)

## Variation of Gain wrt to  different Vicm.

- the Vout remains unchanged when both the Vicm is varied simultaneously, if the Vicm voltages is varied at different directions there is no change in the Vout ,thus gain will remain constant.

V2(50 mV) is given a different input signal than the V1(25 mV).
![image](https://github.com/user-attachments/assets/8994691f-86ea-4dfd-b76b-c7dcba733edd)




### **Circuit 3** <br>

Replace current Source with N-Channel MOSFET .

![image](https://github.com/user-attachments/assets/c08c517f-a53d-4e14-851c-ba44ec7598e7)

V<sub>b</sub> should be less than V<sub>p</sub> as the drain voltage of MOSFET M3 is V<sub>p</sub>

and the V<sub>b</sub> should be greater than the V<sub>th</sub> , therefore the value of V<sub>b</sub> should be between 0.366 V and 0.5V.

### **DC Analysis**

set the operating point of M3 such that It is in saturation state.
V<sub>3</sub>=0.8 V

![image](https://github.com/user-attachments/assets/050d82d5-1117-448b-9bb6-ac9d6098b997)

### Effect of VICM on Vout and Id
Vicm is varried from 0 to 3.3 V.

Variation in Vocm

![image](https://github.com/user-attachments/assets/e1607648-320e-4493-8d90-286040340233)


Variation in Id

![image](https://github.com/user-attachments/assets/4b839f99-6be4-4a80-b9c9-7074b9971699)

| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Drain Current  (Id)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.65V**                            | **1.70V**             | **0.46 mA**                |
| **1.3V**                            | **2.33V**                 | **0.27 mA**               |


### **TRANSIENT ANALYSIS**

![image](https://github.com/user-attachments/assets/910186c3-9e66-4c6d-8cb1-d2a1c997118c)

if Vicm is more then

![image](https://github.com/user-attachments/assets/50acbdec-164a-40e2-afa5-3a8ce1cac397)


### **AC Analysis**


![Screenshot 2025-03-02 223315](https://github.com/user-attachments/assets/d0db6eb8-ab1e-4649-bf22-f65bace10bb8)


## Variation of Gain wrt to  different Vicm.

- the gain remains almost unchanged when both the Vicm is varied simultaneously, if the Vicm voltages is varied at different directions the gain will have slight variation, it has more stability.

  V2(50 mV) is given a different input signal than the V1(25 mV).

![circ3_50mv](https://github.com/user-attachments/assets/f2fc283d-da4a-4edf-9cff-d7e5a8d9e828)


### ""Result and Inference""

| **Parameter** | **Circuit 1** | **Circuit 2** | **Circuit 3** |
|--------------|--------------|--------------|--------------|
| **V(out1)**  | 1.70006 V  | 1.70925 V  | 1.70001 V  |
| **V(out2)**  | 1.70006 V  | 1.70925 V  | 1.70001 V  |
| **V(vp) (Common Mode Voltage)** | 0.502839 V | 0.5V | 0.502822 V |
| **Id(M1)** | 0.000457127 A | 0.0004545 A | 0.00045714 A |
| **Id(M2)** | 0.000457127 A | 0.0004545 A | 0.00045714 A |
| **Id(M3) (Tail Current Source)** | absent | 0.000909(set with ideal current source) | 0.000914281 A |
| **Total Tail Current** | 0.000914253 A | 0.000909 A | 0.000914281 A |

1. When V<sub>ICM</sub> changes there is a change in the output voltage and Drain current.

2. If the input voltage is more then the minimum swing or outside the allowable swing the output wave form deforms, ie it is in triode or cutoff region.
   
3. Circuit 1 is a differential pair with a resistor , cannot be precisely biased.
 
4. Circuit 2 uses an ideal current source, it improves the swing .
  
5. Circuit 3 uses an active current source using NMOS, providing best stability and is more practical for real applications.
**Circuit 3 is the preferred design**.
