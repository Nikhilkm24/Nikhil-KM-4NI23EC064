
# Aim
  Design and analyze the mos differential amplifier circuit for the following specification.

# Components Required
  NMOS,Resistor,voltage source,current source

# Theory
  A differential amplifier rejects common-mode signals by design, leveraging the fact that it amplifies only the difference between the voltages at the two inputs (non-inverting and inverting), while it rejects any signals that are common to both inputs. This ability to reject common-mode signals is due to its common-mode rejection mechanism. 

# Question
  Design and analyse the differential amplifier for the following specification Vdd = 2v , P <=1mw ,Vicm = 1v ,Vocm = 1.1v,Vp = 0.4v.

  Perform:
- DC Analysis
- Transient Analysis
- AC Analysis
- Extract required parameters

# Circuit 1(Resistor)

  ![Screenshot 2025-03-06 001321 - Copy](https://github.com/user-attachments/assets/4c20fb7c-0099-472e-83f1-5df22aa8f375)

# Calculation(theoretical)

| Parameter | Symbol | Value |
|-----------|--------|--------|
| Supply Voltage | Vdd | 2 V |
| Voltage at Source | Vp | 0.4 V |
| Power | P | 1m W |
| Input Common Mode Voltage | Vicm | 1 V |
| Output Common Mode Voltage | Vocm | 1.1 V |
| Source Current | Iss | 0.5m A |
| Drain Current (each transistor) | Id1 = Id2 | 0.25m A |
| Drain Resistance | Rd1=Rd2 | 3.6k ohn |
| Source Resistance | Rss | 800 ohm |

1. **Determine Iss (Source Current):** 
Iss = P / Vdd
Iss = 1*10^-3 /2
Iss = 0.5m A

2. **Calculate Rd (Drain Resistance):**  
Id1 = Id2 = Iss
Id1=Iss/2
Id1=0.25mA

3. **Calculate Rss (Source Resistance):** 
Rd = ( Vdd -Vocm)/Id1
Rd = (2-1.1) / 0.25mA
Rd = 3.6k ohm
 
# *DC Analysis*

### Steps to Perform DC Analysis in LTspice XVII
1. *Open LTspice* and rigup the MOS differential amplifier circuit schematic.
2. *Set Up the Simulation Command:*
   - Click on *Simulate* > *Edit Simulation Cmd*.
   - In the *DC op pnt* tab, select *.op*.
   - Click *OK*, and place the generated command on the schematic.
3. *Check the Component Parameters:*
   - Ensure that the MOSFET models and resistor values match the given specifications.
   - Verify that the power supply voltages (Vdd, Vicm) are correctly set.
4. *Run the Simulation:*
   - Click on *Run*.
     ![image](https://github.com/user-attachments/assets/5b178357-31fd-465d-b53a-0c8b8703df84)

  

# *Transient Analysis*

1. *Open LTspic* and load the circuit schematic.
2. *Set Up the Simulation Command:*
   - Click on *Simulate* > *Edit Simulation Cmd*.
   - In the *Transient* tab, enter a stop time and a step time if needed.
   - Click *OK*, and place the generated command on the schematic.
3. *Apply an Input Signal:*
   - Set a sinusoidal or pulse voltage source at the input nodes.
   - Define the frequency and amplitude of the input signal.
4. *Run the Simulation:*
   - Click on **Run**.
5. *Analyze the Waveforms:*
   - Observe the output waveforms at the differential output nodes.
   - Verify the response and note the phase shift and signal gain.

    ![image](https://github.com/user-attachments/assets/5e53fa2b-3fd3-4eaf-97a0-f831193b0874)

# *AC Analysis*

1. *Set Up the Simulation Command:*
   - Click on *Simulate* > *Edit Simulation Cmd*.
   - In the *AC Analysis* tab, select *Type of Sweep Decade*.
   - Click *OK*.
2. *Set AC Parameters for Input Source:*
   - Ensure the input voltage source is set with an AC amplitude (1V).
3. *Run the Simulation:*
   - Click on *Run*.
5. *Analyze the Frequency Response:*
   - Observe the gain and phase plots.
   
   ![image](https://github.com/user-attachments/assets/1e8c16c4-ddfd-4444-a355-04d67f791434)

- From the above image we can see that there is a **Phaseshift** of 180°.
-  **Gain** of  5.255db.



![image](https://github.com/user-attachments/assets/df47a115-58f9-4e6c-97a6-8a185309f9bf)
## Maximum input swing is 265m V

  # Circuit 2 (Current Source)

## Replacement of resister R3 by Current Source 

![image](https://github.com/user-attachments/assets/8ff78f22-32d6-478a-a968-1f85f5747230)

### What is the requirment of replacing the resister RS by a current source ?
 ---> 1) Replacing Rs with a current source in a differential amplifier improves:
- *Gain – A high-impedance current source increases gain*.
- *CMRR – Reduces common-mode signal interference*.
- *Bias Stability – Maintains a constant tail current*. 
- *Linearity – Provides better signal integrity*.


# *DC analysis*

  ![image](https://github.com/user-attachments/assets/ea5980fd-dd8e-464a-982b-6b81266af807)

  
# *Transient Analysis*

  ![image](https://github.com/user-attachments/assets/4ef2fdb4-af1f-47d9-8c38-78ed9a618fb1)

# *AC Analysis*

 ![image](https://github.com/user-attachments/assets/6210e461-7ee4-4a05-b2c8-6698124efe2b)



# Circuit 3 (Mosfet)

![image](https://github.com/user-attachments/assets/03da15d3-4415-4169-a8b1-bf7eef59f89b)

## What is the requirment of replacing the resister RS and current source by a MOSFET in differential amplifier ?

*In a differential amplifier, we replace the source resistor (Rs) and current source with a MOSFET current mirror for these reasons:*
- *Higher Gain – A MOSFET as a current source provides a much higher output resistance compared to a resistor, increasing gain.*
- *Better Current Matching – A MOSFET current mirror ensures precise current balancing between transistors, improving circuit symmetry*.
- *Improved Common-Mode Rejection (CMRR) – It enhances the amplifier’s ability to reject common-mode signals, making it more stable*.
- *Reduced Voltage Drop – A current source MOSFET requires less voltage headroom than a resistor, improving the amplifier's efficiency*.

### L = 300n
### W =309.919u
![image](https://github.com/user-attachments/assets/7f17dd25-0858-44e3-9701-825a54f24eb8)

**Hence on observing the Vgs-Vt>=Vp**
- Vgs > Vt
- Vds > Vov

##*The MOSFET M3 is in saturation region* 

# *DC Analysis*
![image](https://github.com/user-attachments/assets/9c3f0651-7508-4669-984d-dec2f7d59cd5)

# *Transient Analysis*

![image](https://github.com/user-attachments/assets/18c9611b-8272-48af-9946-36e0665c686c)

# *AC Analysis*

![image](https://github.com/user-attachments/assets/3bb2809e-7dcb-4a68-a620-caf16465d0a4)


# **Final Result Comparition**
| **Parameter** | **Circuit 1** | **Circuit 2** | **Circuit 3** |
|--------------|--------------|--------------|--------------|
| **Vo1**  | 1.1V  | 1.1V  | 1.1V  |
| **Vo2**  | 1.1V  | 1.1V  | 1.1V  |
| **Vp** | 0.4V | 0.4V | 0.4V |
| **Id1** | 0.25m A | 0.25m A | 0.25m A |
| **Id2** | 0.25m A | 0.25m A | 0.25m A |
| **Iss** | 0.5m A | 0.5m A | 0.50000003m A |


# *Inference :* 
## Overview of Circuits

### Circuit 1: Resistor-Based Current Source
- Uses a **800Ω resistor** as the current source.
- **Simple** but not very stable.
- Tail current varies with supply voltage and temperature.

### Circuit 2: Ideal Current Sour
- **Highly stable**, but not practical for real-world use.
- Mainly used for theoretical and AC analysis.

### Circuit 3: Active NMOS Current Source
- Uses an **NMOS transistor as a current source**.
- **Best stability**, making it the most practical design.
- Automatically adjusts to maintain a steady tail current.

## Stability of Tail Current

| Circuit  | Current Source | Stability | Notes |
|----------|---------------|-----------|-------|
| **Circuit 1** | Resistor  | Low | Affected by voltage and temperature changes. |
| **Circuit 2** | Ideal Source  | High | Theoretically perfect, but impractical. |
| **Circuit 3** | NMOS Transistor | Highest | Best for real applications due to auto-adjustment. |

## Why Circuit 3 is the Best Choice
- **Adds an extra transistor (M3)** to improve current stability.
- **Keeps current balanced** between M1 & M2.
- **Minimizes voltage and temperature effects** on performance.

## Voltage & Current Comparison

- **Output Voltage**:
  - Circuit 1: **1.1V** (out1, out2)
  - Circuit 3: **1.1V** (out1, out2)
  - Circuit 3 has slightly better voltage regulation.

- **Drain Current**:
  - Circuit 1: **0.25m A** (M1, M2)
  - Circuit 3: **0.25m A** (M1, M2) 
  - Circuit 3 maintains a steady current using M3 (**0.5m A**).

##  Key Inference from Experiment
- A **resistor-based current source (Circuit 1)** is simple but unstable, making it unreliable for real-world applications.
- An **ideal current source (Circuit 2)** provides perfect stability but is impractical in actual circuits.
- An **active NMOS current source (Circuit 3)** balances practicality and stability, making it the most effective choice.
- **Adding M3 ensures stable tail current, reducing voltage fluctuations and enhancing overall performance.**

Circuit 3 is the one of the best circuit among above circuits for differential amplifier designs because it:
-  Offers **superior stability**
-  **Minimizes supply voltage variations**
-  Provides a **constant, regulated tail current**

🔹 **If you're designing a real-world differential pair, Circuit 3 is your best bet!** 



 
