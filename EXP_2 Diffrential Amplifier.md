
# Aim
  Design and analyze the mos differential amplifier circuit for the following specification.
# Components Required
  NMOS,Resistor,voltage source,current source
# Theory
  A differential amplifier rejects common-mode signals by design, leveraging the fact that it amplifies only the difference between the voltages at the two inputs (non-inverting and inverting), while it rejects any signals that are common to both inputs. This ability to reject common-mode signals is due to its common-mode rejection mechanism. 
# Question
  Design and analyse the differential amplifier for the following specification Vdd = 2v , P <=1mw ,Vicm = 1v ,Vocm = 1.1v,Vp = 0.4v perform DC analysis , transient analysis,frequency response and extract the required parameters. 
# Circuit 1(Resistor)
 
# Calculation(theoretical)
  Vdd = 1.8v

  Vp = 0.4v

  P = 2.2mw

  Vicm = 0.95v
  
  Vocm = 1.11v
  
  Iss = P/v
  
   = 2.2*10^-3 /1.8
   
  Iss = 1.2222 mA
  
Id1 = Id2=Iss/2=0.611mA

Rd =( Vdd -Vocm)/Id1

   = (1.8-1.11)/0.611*10^-3
   
   = 1.145k ohm
   
   Rss = Vp/Iss
   
  = 0.4/1.22*100^-3

Rss = 327.33 ohm

# DC Analysis
  since to get apropiate Id obtained in theoretical we should vary w/l
  so for this circuit
  
   W = 180nm
    
   L = .109*10^-3 m
   
   
![WhatsApp Image 2025-03-02 at 22 49 22_652ecb05](https://github.com/user-attachments/assets/42f119bd-2ca4-4ca5-8060-1b5a8d8fcc1c)



Q point = (Vgs,Id) = (0.5497v,0.611mA)

Now we can vary vdd so that we can know how the q point varies accordingly
for Vg

vg = 0.95v Q point = (0.5945v,0.611mA)

vg = 1.15v Q point = (0.584326v,0.864mA)

vg = 1.1v Q point = (0.575245v,0.80157mA)

vg = 0.80v Q point = (0.52187v,0.424mA)

vg = 0.70v Q point = (0.5002v,0.3052mA)

# AC analysis

 ![WhatsApp Image 2025-03-02 at 23 03 50_8a6f6575](https://github.com/user-attachments/assets/7def2159-0694-44a4-9257-5094847f63a7)


# Transient Analysis

 ![WhatsApp Image 2025-03-02 at 23 02 52_e8f90c75](https://github.com/user-attachments/assets/a21053cd-98b3-4c64-9aa2-ed217e1c0d04)

 # loop gain 

  Av = 14.47dB


  # Circuit 2 (Current Source)

  ![WhatsApp Image 2025-03-02 at 23 11 37_f42b2205](https://github.com/user-attachments/assets/347a445f-920b-40b8-a1e5-aee08ce7daa4)


: Here Resistor is replaced by Current Source

: Since the common mode is rejected by an differential ampifier so we give seperate inputs Mosfet

# DC analysis

   ![WhatsApp Image 2025-03-02 at 23 05 46_f3bb1f8c](https://github.com/user-attachments/assets/7279138c-18f6-4efa-bb41-97534d1ce5ba)


# AC Analysis

![WhatsApp Image 2025-03-02 at 23 12 33_3215bd9d](https://github.com/user-attachments/assets/6488f4da-d77a-4884-943b-eaceda30c7b3)


# Transient Analysis

![WhatsApp Image 2025-03-02 at 23 11 04_a584b77d](https://github.com/user-attachments/assets/17840274-678d-48f2-8803-bdca062c3a4b)

# Loop Gain

Av = 11.3726 dB


# Circuit 3 (Mosfet)

![WhatsApp Image 2025-03-02 at 22 43 44_cb42ec7e](https://github.com/user-attachments/assets/df5ba3c5-13a1-49d3-8f5c-ba43cf984952)

: Here the resistor is replaced by an Mosfet.

: We should set appropiate Vb value to make mosfet to work 

: For this Mosfet the Vb which we given is 0.6v because it should be greater than vt.

: the W/L we choosen is

L = 180nm

W = 68.8*10^-6 m


# DC Analysis
![WhatsApp Image 2025-03-02 at 22 46 17_0f1c69f3](https://github.com/user-attachments/assets/b5604c74-3583-460b-b097-38fece417a60)

# AC Analysis
![WhatsApp Image 2025-03-02 at 22 44 48_ea4c58df](https://github.com/user-attachments/assets/d4272b93-51ce-4e66-9f91-136d9d6467eb)

# Transient Analysis 

 ![WhatsApp Image 2025-03-02 at 22 42 42_5a0d5801](https://github.com/user-attachments/assets/da9608fd-1bea-4123-afe2-92ab8bbc705c)

 # Loop gain
  Av = 14.19dB

# Result
The result obtained from the analysis is matched with theoretical values from that we can conclude that design obtained is correct.


# Inference
The differential amplifier successfully amplified the differential signal and rejected the common-mode signal as expected. The results confirm that the amplifier operates as designed, with a high ability to reject noise or interference that is common to both inputs.Even when we given  a common mode voltage it shows wrong graphs and obtained results are not correct.















 
