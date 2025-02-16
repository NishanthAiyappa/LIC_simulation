## Experiment 1: Simulation and Design of CS Amplifier

### **Aim**
Simulate the DC analysis, Transient, and AC analysis of a CS amplifier circuit using LTSpice.

### **Procedure**

1. **Design the CS amplifier circuit.**
2. **Naming the NMOS** as `CMOSN`.
3. **DC Analysis:**
   - Apply the DC voltage of \( V_{DD} = 1.8V \) and \( V_{GS} = 0.9V \).
   - In LTSpice, go to the **Simulate** option and select **Edit Simulation Command**.
   - Click on **DC Analysis**, then press **OK**.
   - Click on **Run** in the tab menu to obtain the **DC operating point** \( V_{out} \).
   - Set the **Length** as constant and determine the **Width** such that \( I_{D} = 55.5 \mu A \).

4. **Transient Analysis:**
   - Modify the \( V_{GS} \) voltage source to a **sine wave input** with:
     - DC level: \( 0.9V \)
     - Amplitude: \( 50mV \)
     - Frequency: \( 1kHz \)
   - In LTSpice, go to **Edit Simulation Command**, select **Transient Analysis**.
   - Set the **Stop Time** as **5ms**, then click **OK**.

5. **AC Analysis:**
   - In **Edit Simulation Command**, select **AC Analysis**.
   - Set the **Type of Sweep** to **Decade**.
   - Set **Points per Decade** to **10**.
   - Set the **Frequency Range** from **0.1Hz to 1THz**.
   - Click **OK**.
   - Determine the **gain** and **frequency response** of the circuit.

### **Calculation**

#### **Power Calculation**
\[ P = 100 \mu W \]

#### **Drain Equation**
\[ V_{DD} = V_{DS} + I_{D} \times R_{D} \]

\[ P = I \times V \]

Given: \( I_D = 55.5 \mu A \), \( V_{DD} = 1.8V \)

Since \( V_{DS} = V_{out} \), we ensure:
\[ V_{DS} \geq V_{GS} - V_{th} \]
