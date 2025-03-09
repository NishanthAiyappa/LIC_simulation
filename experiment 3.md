
### **Differential Amplifier**

A differential amplifier is a key circuit in analog electronics that amplifies the difference between two input signals while rejecting common-mode signals (noise). It is widely used in operational amplifiers (op-amps), instrumentation amplifiers, and analog circuits.
A basic MOSFET differential amplifier consists of:

Two matched MOSFETs (M1 and M2) forming a differential pair

A current source I<sub>SS</sub> as a tail current

Two drain resistors R<sub>D</sub>

When the inputs V<sub>in1</sub> and V<sub>in2</sub> are equal, the circuit is balanced, and the current splits equally.

When V<sub>in1</sub> increases while V<sub>in2</sub> decreases, M1 conducts more current, and M2 conducts less, creating a voltage difference at the outputs.

The circuit rejects common-mode signals (same voltage at both inputs) and only amplifies the differential component

### **question:**

**V<sub>DD</sub>=3.3 V , p<=3 mW , V<sub>ICM</sub>=1.65 V, V<sub>ocm</sub>=1.7 V , V<sub>P</sub>=0.5 V**

**Circuit 1** <br>

![image](https://github.com/user-attachments/assets/6caf6b0a-5821-4259-8b8d-80fce68f4cb9)

**Step 1:Dc analysis design Rd and Rss**
![image](https://github.com/user-attachments/assets/f7a39423-0de0-439c-b98a-217d4620e004)

from the calculation we have finded I<sub>SS</sub>value as 0.909 mA <br>
I<sub>D1</sub> and I<sub>D2</sub> as 0.45 mA <br>
R<sub>D</sub> as 2.5 kohm <br>
R<sub>SS</sub> as 550 ohm <br>
V<sub>GS</sub>=V<sub>G</sub> - V<sub>p</sub> = 1.65 V - 0.5 V = 1.15 v <br>
V<sub>OV</sub> = V<sub>GS</sub> - V<sub>th</sub> = 1.15 V - 0.366 V = 0.784 V <br>

### **DC Analysis**

To set the operating point go to Configure Analysis and select Dc operating Point <br>

![image](https://github.com/user-attachments/assets/11c557c2-3210-4b50-9a06-5f3bd5e15e0d)


to set correct operating point vary width and length values 
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
go to configure Analysis and select transient analysis then <br>
stop time as 1m ,time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• DC Offset: 1.65 V
• Amplitude: 25 mV
• Frequency: 1 kHz

put the same values for V2 but change the phase angle.

And in V2 phi(deg) as 180
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

if vin is more then

![image](https://github.com/user-attachments/assets/50acbdec-164a-40e2-afa5-3a8ce1cac397)


### **AC Analysis**


![Screenshot 2025-03-02 223315](https://github.com/user-attachments/assets/d0db6eb8-ab1e-4649-bf22-f65bace10bb8)


### ""Result and Inference""

V<sub>DD</sub>=3.3 V

V<sub>p</sub>=0.5 V

V<sub>ICM</sub>=1.65 V 

V<sub>OCM</sub>=1.7 V

R<sub>D</sub>=3.5 kohm

R<sub>SS</sub>=550 ohm

I<sub>SS</sub>=0.909 mA

I<sub>D</sub>=0.45 mA

1. When V<sub>ICM</sub> changes there is a change in the output voltage and Drain current.

2. If the input voltage is more then the minimum swing or outside the allowable swing the output wave form deforms, ie it is in triode or cutoff region.

3. If R<sub>D</sub> value changes there will be a change in the output voltage,by selecting the resistance wecan control the output voltage.

4. V<sub>b</sub> should be less than V<sub>p</sub> as the drain voltage of MOSFET M3 is V<sub>p</sub>
and the V<sub>b</sub> should be greater than the V<sub>th</sub> .















































 
