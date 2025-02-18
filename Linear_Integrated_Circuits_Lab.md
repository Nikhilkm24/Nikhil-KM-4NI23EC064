# Experiment-1

## Aim
To perform DC analysis, Transient analysis, and AC analysis of a Common Source (CS) amplifier circuit using LTSpice and extract the various associated parameters.

## Components Required
- **MOSFET** (nmos4, pmos4)
- **Resistor** (1k)
- **Voltage Supply** (1.8V, 0.9V)
- **Connecting Wires**

## Theory
MOSFET is one of the most essential components in electronics due to:
- Compact design
- Low power consumption
- Simple geometry
- Compatibility with VLSI technology

### MOSFET Configurations
- **Common Source (CS)** (most widely used)
- **Common Drain**
- **Common Gate**

### Common Source Amplifier
- Operates in **saturation region** where:
  - V_gs > V_th
  - V_gd < V_th
  - V_ds geq V_ov
- 180-degree phase shift between input and output
- High input impedance (ideally infinite)
- Output taken from drain end to maintain common ground reference

---

### DC Analysis
- Ensures MOSFET operates in saturation
- Determines the **DC operating point** to prevent signal distortion
- Helps in bias resistor calculation
- Maintains a correct operating point despite parameter fluctuations

### Transient Analysis
- Analyzes response to time-varying signals
- Determines **signal distortion** and **DC shift** between input and output
- Detects **phase distortion**
- Essential for **high-speed applications**

### AC Analysis
- **Small signal analysis**
- Determines **gain** of the amplifier circuit: \( A_v = -g_m R_d \)
- Analyzes **frequency response** of the amplifier

---

## Procedure
1. **Create a new folder** and save the LTSpice file in this directory.
2. **Set MOSFET parameters:**
   - NMOS: Name as `CMOSN`, Length = **180nm**, Width = **3um**
   - PMOS: Name as `CMOSP`, Length = **180nm**, Width = **3um**
3. **DC Analysis:**
   - Apply **Vdd = 1.8V**, **Vgs = 0.9V**
   - Run `.op` command in LTSpice to extract **DC operating point**
4. **Transient Analysis:**
   - Apply **sinusoidal input**: **Vgs = 0.9V**, Amplitude = **50mV**, Frequency = **1kHz**
   - Run `.tran 3m` to observe **time-domain response**
5. **AC Analysis:**
   - Specify frequency sweep from **0.1Hz to 1THz** with **20 points per decade**
   - Run `.ac dec 20 0.1 1T` to analyze **gain & frequency response**

---

## Circuit 1  
![image](https://github.com/user-attachments/assets/fb66878c-4309-4919-8001-34675b50916f)

### Given:
- Power = **50µW**
-  V_dd = 1.8V 
-  V_gs = 0.9V 
-  R_d  = **1KΩ**
- Width varied to obtain the required current
- Q-point: **(1.7773V, 27.77µA)**
## Results 
## 1) DC Analysis:
![image](https://github.com/user-attachments/assets/24e3b15d-200e-42bb-a80a-e5cf43933b76)
 - Id=27.uA
 - Vout=1.7773V
 - Width=97.25um
 - DC Operating point : (1.773,27uA) is obtained for 97.25um Width and 180nm Length.

## 2) Transient Analysis:
![image](https://github.com/user-attachments/assets/c82abafa-6338-49bc-bad5-06ab693d8cbe)
![image](https://github.com/user-attachments/assets/512a4a92-c9b5-4cee-92f6-d0917eea0b58)
![image](https://github.com/user-attachments/assets/09c49ef0-6b76-4fdf-9362-00987283e662)
 
 - Vout=1.773V (From Graph)
 - There is 180 degree phase shift between input and output or the DC level shift.

## Ac Analysis
![image](https://github.com/user-attachments/assets/8d0f7aad-b656-4e24-907e-790a15febd36)

 - Gain = -20 dB


### Inference 
Inference:
1) Current is directly Propotional to the Width of the Mosfet and the current varies with the change in width.

2) Mosfet saturation ensures the mosfet works as an amplifier and produces the desired negative gain as per the equation Av=-gm*Rd.

3) Q point stability is attained in saturation region thus helping in attaining linear amplification .

4) The Mosfet gain is increased in mid band frequency range (small signal analysis).

5) The Transient analysis reveleas the response of the circuit to time domain ssignal and determines how quickly the circuit responds to variation.
This is essential in high speed applications.

6) AC Analysis helps in designing circuits with desired gain and helps in impedance matching.
Also helps in understanding the frequency response and small signal behaviour of the circuit.
---



# Expriment 2:
## Inverted CS Amplifier Analysis

## Introduction
The objective of this report is to evaluate the inverting behavior of a CS amplifier when it operates on both DC and AC sources.

## NMOS and PMOS Specifications

| Configuration | Connection |
|--------------|------------|
| **PMOS** | |
| Source | Connected to supply (1.8V) |
| Gate | Connected to 0.9V |
| Drain | Connected to NMOS drain |
| **NMOS** | |
| Source | Grounded |
| Gate | Connected to 0.9V |
| Drain | Connected to PMOS drain |

## Circuit 2 
![image](https://github.com/user-attachments/assets/45995b7b-e78c-4049-9341-1fc089e6b7e5)


### Given:
- ( P = V *I  ), where ( V = 1.8V )
- ( I_d = 27.77uA )
- ( V_{out} = 1.658V )
- Length = **180nm**
- Width = **3um**

## DC Analysis

![image](https://github.com/user-attachments/assets/6e0c7469-669e-460d-929b-acc9d5b69272)



Our approach in conducting DC analysis involves identifying the quiescent operating point (ID) and node voltages that are required to operate the MOSFET.

| Parameter | Value |
|-----------|--------|
| Supply Voltage (VDD) | 1.8V |
| Gate Voltage (VG) | 0.9V |
| Power Budget (P) | 50uW |

### Calculation:

P = VDD * ID
ID = P / VDD
ID = 50uW / 1.8V
ID = 27.7uA
- Thus, the drain current (ID) is found to be **27.7uA**.


## AC Analysis 
![image](https://github.com/user-attachments/assets/33c8e533-6a24-4543-b258-976308e2c893)



- A sinusoidal input is included in the AC analysis through a modification of gate voltage.
- Sinusoidal Input Voltage
DC Offset: 0.9V
Amplitude: 50mV
Frequency: 1kHz
Frequency Sweep Parameters

Type: Decade
Sweeps per Decade: 20
Start Frequency: 0.1Hz
Stop Frequency: 1THz

## Transient Analysis
![image](https://github.com/user-attachments/assets/f397177f-543d-4034-9371-921cdfb9aa2e)

- The voltage present at the drain terminal of the NMOS transister.

![image](https://github.com/user-attachments/assets/b7d58318-01f7-4199-ad91-d51552d3087b)

- The voltage present at the gate terminal of the NMOS transister.

![image](https://github.com/user-attachments/assets/128d035c-8ef6-4c4b-a4f2-a08ec8cee33f)

- On comparing the input and output voltage we will get to know the phaseshift of 180 degree. 

![image](https://github.com/user-attachments/assets/4863e27a-4aed-42e4-aba7-1d8900223db5)

- Here From the above we will get to know that Current Id=27uA

---

## Inference
- The amplifier's behaviour is altered when a PMOS transistor is used in place of the resistor (1KΩ), creating an active load arrangement.
The DC operating point of the new circuit is 1.799V, 27.7μA.
Enhanced Output Response and Gain
- Higher amplification from the active load is confirmed by the gain, which rises noticeably to -70 dB.
ensures correct functioning within the specified power restrictions by stabilising at 1.799V.
The 180-degree phase shift is constant.
- The transient analysis shows that the inverted CS amplifier retains the same inverting behaviour as a regular CS amplifier by confirming a continuous 180-degree phase shift.
Realistic Aspects and Use
- Integrated circuit (IC) designs benefit greatly from the active load arrangement (PMOS rather than a resistor) in high-gain and low-power applications.

## Conclusion
- The effect of MOSFET width on Q-point stability and drain current.
- The CS amplifier's capacity to do both signal amplification and phase inversion.
- How to improve amplifier performance and boost gain by substituting an active PMOS load for a resistor.
- The importance of transient, DC, and AC studies in the design and optimisation of MOSFET-based amplifiers for a range of practical uses.
- This study demonstrates that CS amplifiers, whether resistor-loaded or PMOS-loaded, may be efficiently constructed to meet the requirements of many applications, including high-speed, low-power, and high-gain circuits.






