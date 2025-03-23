# Design and Analysis of Current Mirror Circuit
### 1. AIM   :

### Design question A
Design and analyse the current mirror circuit for the following specifications.
- Av > -10 V/V
- V<sub>DD</sub> = 1.8 V
- P <= 1 mW

Perform the DC analysis, Transient analysis and AC analysis while maintaining (W/L) same for different values of Length(L). ALso find the maximum output swing and bandwidth.
### 2.Theory:
A current mirror is a circuit used to copy (mirror) a reference current from one branch to another while maintaining a constant current. It is widely used in analog circuit design, such as biasing circuits and active loads in amplifiers.

## Principle of Operation
A current mirror operates based on the concept that two identical transistors, when subjected to the same V_BE (base-emitter voltage), will conduct the same current, assuming they have identical characteristics
 
 A reference current I<sub>REF</sub> is forced through M1, setting its gate-source voltage  V<sub>GS</sub>.
-  The gate of M1 is connected to M2, ensuring that both transistors have the same V<sub>GS</sub>.
-  Since both transistors are identical, M2 will conduct a current equally.
-  Current Copying Ensures that the output current remains identical to the reference current.
-  Output current remains constant despite changes in the load.
### for 1:1 Ratio
### 3.1 Ciruit Design


1. Determine the Total current (I<sub>TOTAL</sub>)

   I<sub>TOTAL</sub> = P/V<sub>DD</sub>= 1.8 V = 1 m/1.8 = 0.555 mA

2. Determine the reference current ( I<sub>REF</sub>)

  I<sub>TOTAL</sub>=  I<sub>REF</sub>+ I<sub>D</sub>
  
  I<sub>REF</sub> = I<sub>TOTAL</sub>/2 = 0.555m/2 = 0.277 mA

  ![image](https://github.com/user-attachments/assets/447ece28-ac43-4665-80a8-c03dfc3096f5)

|Parameters | PMOS(M1)| PMOS(M2) | NMOS(M3) |
|-----|----|----|----|----|----|-----|
| Length| 180nm |180nm | 180nm | 
| Width | 2.5um | 2.5um | 2.9um | 

 ### 4.1 Simulation.
 ### DC Sweep.
 By doing a DC Sweep we can determine the Q-point.
 
 ![image](https://github.com/user-attachments/assets/e7c92f57-6916-46c1-afba-56c41fc11b9f)

from the above graph we can set the biasing voltage as 0.85 V. 
 ### DC Analysis
 
 ![image](https://github.com/user-attachments/assets/315d8e80-e30b-43b3-8125-a9d5f803c825)


 

 
 
