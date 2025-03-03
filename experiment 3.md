
### **"Differential Amplifier"**

A differential amplifier is a key circuit in analog electronics that amplifies the difference between two input signals while rejecting common-mode signals (noise). It is widely used in operational amplifiers (op-amps), instrumentation amplifiers, and analog circuits.
A basic MOSFET differential amplifier consists of:

Two matched MOSFETs (M1 and M2) forming a differential pair

A current source I<sub>SS</sub> as a tail current

Two drain resistors R<sub>D</sub>

When the inputs V<sub>in1</sub> and V<sub>in2</sub> are equal, the circuit is balanced, and the current splits equally.

When V<sub>in1</sub> increases while V<sub>in2</sub> decreases, M1 conducts more current, and M2 conducts less, creating a voltage difference at the outputs.

The circuit rejects common-mode signals (same voltage at both inputs) and only amplifies the differential component

### **question:V<sub>DD</sub>=3.3v , p<=3mW , V<sub>ICM</sub>=1.65v, Vocm=1.7v , V<sub>P</sub>=0.5v**

**Circuit 1** <br>

![ci](https://github.com/user-attachments/assets/fcbc06b1-b816-4f9f-a97c-0958f0cc0b90)

**Step 1:Dc analysis design Rd and Rss**

![image](https://github.com/user-attachments/assets/177acc0c-146e-4b17-9728-f7603b3e3047)

from the calculation we have finded Iss value as 1mA <br>
Id1 and Id2 as 0.5mA <br>
Rd as 3.5kohm <br>
Rss as 550ohm <br>
Vgs=vg - vp = 1.65v - 0.5v = 1.15v <br>
Vov = vgs - vth = 1.15v - 0.366v = 0.784v <br>

### **DC Analysis**

To set the operating point go to Configure Analysis and select Dc operating Point <br>

![dc2](https://github.com/user-attachments/assets/f76e42bb-74e2-496f-b76f-efc2412a4067)

to set correct operating point vary width and length values 
width = 208u <br>
length = 6u <br>


### **Analysis**

### Effect of VICM on Vout and VP

| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.65V**                            | **1.70V**             | **0.5V**                |
| **1.3V**                            | **1.62V**                 | **0.59V**               |



As the common-mode input voltage \( VICM \) increases, the source voltage \( VP \) also increases, causing a shift in the operating point. This leads to a higher drain current, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).


### **Calculate maximum input and output Swing**

![image](https://github.com/user-attachments/assets/f7a39423-0de0-439c-b98a-217d4620e004)


### **TRANSIENT ANALYSIS**
go to configure Analysis and select transient analysis then <br>
stop time as 1m ,time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• DC Offset: 1.65 V
• Amplitude: 25 mV
• Frequency: 1 kHz

put the same values for V2 but change the phase angle.

And in V2 phi(deg) as 180

![image](https://github.com/user-attachments/assets/5f94dcd4-4c40-4ab4-93b0-b64ba6fabf10)

when the input voltage is more then the minimum swing or outside the allowable swing the output wave form deforms, ie it is in triode or cutoff region.

![diform](https://github.com/user-attachments/assets/afb2f26a-64ab-4c48-8c14-043b88c2a829)


### **AC Analysis**
• Type of sweep: Decade
• Number of points per decade: 10
• Start frequency: 0.1 Hz
• Stop frequency: 1 THz
AC Amplitude as 1 and AC Phase as 0 in V1 <br>
AC Amplitude as 1 and AC Phase as 180 in V2 <br>

![Screenshot 2025-03-02 235653](https://github.com/user-attachments/assets/db083118-03a3-4021-8a05-7e8285b9bea3)

![Screenshot 2025-03-02 215847](https://github.com/user-attachments/assets/832d0f56-d7ed-4f4a-b0cb-d0fc4634f410)

![Screenshot 2025-03-02 220006](https://github.com/user-attachments/assets/ecfef7ef-22da-4aa5-93b4-74fba38dd18f)


### **Circuit 2** <br>

Replacing Resistor with Current Source 

![Screenshot 2025-03-02 222734](https://github.com/user-attachments/assets/dc70cd6c-eed5-4693-bb86-b6c9e4096b61)

### **DC Analysis**

![Screenshot 2025-03-02 222935](https://github.com/user-attachments/assets/d922b434-5aa1-4bb5-8855-bf281f8d0f53)

![Screenshot 2025-03-02 223027](https://github.com/user-attachments/assets/7ed89486-72bf-409c-a950-a7bc6410a323)

### **AC Analysis**

![Screenshot 2025-03-02 235653](https://github.com/user-attachments/assets/698fa1bf-381b-4deb-a83d-4cf1f8227d05)

![Screenshot 2025-03-02 223315](https://github.com/user-attachments/assets/d0db6eb8-ab1e-4649-bf22-f65bace10bb8)

### **TRANSIENT ANALYSIS**

![Screenshot 2025-03-02 224140](https://github.com/user-attachments/assets/e68ff7b8-09b1-4afa-9d31-49f6f7a2c907)

![Screenshot 2025-03-02 224947](https://github.com/user-attachments/assets/f1914323-d85a-4be8-a213-21e988cb0678)

![Screenshot 2025-03-02 225541](https://github.com/user-attachments/assets/e4d83695-4ca3-460d-972c-5aeafdbbca74)

### **Circuit 3** <br>

Replacing current Source with MOSFET 

![Screenshot 2025-03-03 000910](https://github.com/user-attachments/assets/3b155209-c3eb-4a34-b1ed-1a664c0c2067)

How to find Vb?
Vb = vth + Vp <br>
Vb = 0.366v + 0.4v <br>
Vb = 0.766v <br>

### **DC Analysis**

To set the operating point vary 3rd MOSFET width and keep length as same before 
For approx operating Point i got width as 17.75u

![Screenshot 2025-03-03 001117](https://github.com/user-attachments/assets/b8eab2f6-7e14-4b52-b01e-cfe42d79ec75)

### **AC Analysis**

### **TRANSIENT ANALYSIS**

### ""Result and Inference""

### **Circuit 4**
Replace two resistor with PMOS Transistor

![Screenshot 2025-03-03 054151](https://github.com/user-attachments/assets/3bddfece-f2be-4f60-9caf-61d53a124653)

### **DC Analysis**

### **AC Analysis**

### **TRANSIENT ANALYSIS**

### ""Result and Inference""














































 
