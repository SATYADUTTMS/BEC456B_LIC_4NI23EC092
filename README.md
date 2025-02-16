# Expt_1_CS_Amplifier
This file contains the Experiment 1 CS Amplifier files.

MOSFETs or Metal Oxide Semiconductor Field Effect Transistor plays an important role in our day to day life because of its advantages, characteristics and numerous applications.
It can be used as a "Switch" as well as an "Amplifier". These are the 2 primary applications of MOSFETS.
There are different configurations of MOSFETs being used namely 

1.Common Source Amplifier (CS)

2.Common Gate Amplifier   (CG)

3.Common Drain Amplifier  (CD)

Out of which Common Source Amplifier has an advantage as offers a high voltage gain, good input impedance, and a relatively low output impedance compared to Common Gate and Common  Drain .

The below is the general representation of a CS Amplifier.

![Image](https://github.com/user-attachments/assets/b4af6e83-4f0e-43cd-bf48-05dd4049256e)

We observe that it consists of an NMOS ( N Channel MOSFET ) , whose gate terminal is connected with the Input voltage, the Vin applied has to be greater than the threshold voltage for the channel to form such that the current flows( drain ).

In order to supply power for the circuit , a DC Power supply has been provided at the drain terminal. The Source terminal is connected to the ground.

The drain current flows from supply to the source.Here the applied input is a voltage and we are interested to find the Output Voltage which is been amplified.

Since the MOSFET is a voltage controlled Current device , the output is the drain current. To convert this current to voltage. By Ohm's Law we observe V= I * R. Thus by applying a Resistor at the drain terminal converts this drain current to voltage.

Thus from the Output curves we know that the amplifier works in Saturation Region of MOSFET.

![Image](https://github.com/user-attachments/assets/355e4f53-38ff-442c-b070-0b76902e7f58)

A Q-point (quiescent point) is set in a MOSFET to ensure it operates within its optimal region, providing the desired level of amplification and minimizing distortion and providing a stable DC operating point and also allowing for the largest possible signal swing without clipping or entering non-linear regions.

![Image](https://github.com/user-attachments/assets/0bafae23-8bdc-4ad5-834f-42f12564553e)

The input DC Voltage can also be set using the Voltage divider bias rule at the gate terminal.

Capacitors are the components which act as AC Short and DC open. In other words , it allows AC Component and blocks the DC Component. However the impedance of capacitor also comes into play which will be taken during the various frequency resposnse of the system.

![Image](https://github.com/user-attachments/assets/484075a9-8943-4d6b-8196-0f02e17bedb7)

The below is the Voltage Transfer Curve ( Vds VS Vgs ) for a MOSFET.

![Image](https://github.com/user-attachments/assets/c12fe0eb-9a8f-4560-8c02-c3bfd965241b)

Its observed that when Vgs < Vth, the MOSFET is OFF , as a result Vds = Vdd. However When Vgs > Vth the MOSFET is ON , and if Vds >= Vov it works in Saturation Region (as required). Also if Vds < Vov the MOSFET works in Triode Region.

Now, why do we need Saturation Region ? If observed in the figure we get to know that the curve becomes almost linear in the saturation region. In an input is applied to this region the amplification is at maximum ( higher gain ). So this almost-linear region plays an important role during setting the Q-point.

An 180 deg phase shift is observed at the output. We observe that :

![Image](https://github.com/user-attachments/assets/fc3c815f-4119-42ac-bc6d-d4a869e4f8e5)

And as a result in the input voltage increases the drain current (Id) increases, as a result the Id*Rd term increases. So the Vds value decreases with increase in Vgs . Thus its inverting.

It should also be noted that the input ac signal that we are providing has to be vgs << 2vov for proper operation of amplifier. Other wise if the positive peak is increased, then the negative side will go into the triode region and causes distortion. Also, if the negative side is increased, then the positive side will go into the cutoff region leading to clipping off of signal.

By carefully going and calculating all the parameters and applying an AC signal, its possible to get a very high gain. However we are not interested in such a high value of gain. In order to reduce and stabilize the gain at a good level, we apply a source resistor that acts as source degeneration leading to steady and stable gain.Also, by applying a bypass Capacitor the Gain increases as it helps the unwanted AC signal to bypass the source resistance.

A complete model looks something like this:

![Image](https://github.com/user-attachments/assets/1a555326-9883-4c21-87b3-d5b4f75c2e7b)

Now coming to the frequency response of the CS Amplifier,

![Image](https://github.com/user-attachments/assets/88a55736-efac-4362-9d47-7f62ad536e44)

Its observed that capacitive impedances come into play for lower frequencies and Mosfet capacitances also play a role at higher frequencies. Thus the difference between the Upper Cutoff frequency and Lower Cutoff frequency that is the midband frequency is the frequency range where no capacitive effect comes into play for the CS Amplifier and all the Capacitors acts as AC Short.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Q. CS Amplifier design  having a power budget of 50 microwatt and supply voltage of 1.8v. Input signal 50mV, frequency of 1kHz and tsmc018.lib file for LTSpice.

CIRCUIT :

![Image](https://github.com/user-attachments/assets/281e3033-c79c-49b7-b47e-9be41cd80bfe)


CALCULATION :

Power = Voltage * Current

Current = Power / Voltage = 50u / 1.8 = 27.77 uA.

Since its an Amplifier to make sure that its present in Saturation Region.

Here we observe Vgs = 0.9V and Vt = 0.366V (given) , Also Vgs - Vt = Vov = 0.9-0.366== 0.534V
Thus by fundamental concept , Vds >= Vov , here 1.77V > 0.534V . Its in SATURATION .

With having L = 800nm and W = 785n, the drain current of (approx.) = Id == 27.76 uA is calculated and verified.

1. DC Operating Point :

![Image](https://github.com/user-attachments/assets/e4a05b73-8d19-4aa1-98a6-ee215f6b239a)

2. Transfer Characteristics (Id Vs Vgs):

![Image](https://github.com/user-attachments/assets/2c1412f4-771a-4783-b3cc-08904f4fe53b)


3. Drain Characteristics (Id Vs Vds): 

![Image](https://github.com/user-attachments/assets/e1223250-eb20-4b83-b83c-d9e2c01eea5a) 
 

4. Transient Analysis:

   a. For Vin:

![Image](https://github.com/user-attachments/assets/16d5584e-6e47-46b2-8354-9260c28d5e61) 

   b. For Vout:

![Image](https://github.com/user-attachments/assets/b8a63195-c0a7-4bf4-8e7b-70c7f8f7e921) 

   c. Both:




5. Frequency Analysis:

![Image](https://github.com/user-attachments/assets/269be566-0868-46c4-9846-8419fdfec0da) 

It was observed that Gm came out to be as follows :

![Image](https://github.com/user-attachments/assets/db0abada-5bcc-44bc-b00b-320fcc806720)  

and Thus by using Gain = Gm * Rd we found the Gain to be 1.05*10^-4 * 25k == -2.625.

If we would have used Rd as 1k then my Gain will be 0.105. To increase the gain we have increased the Rd Value.

Some extra Observations :

6. Plot of Id Vs L:

![Image](https://github.com/user-attachments/assets/8494c6c3-fd3b-440e-b7ac-68bcd1bf1488)

7. Plot of Id Vs W:

![Image](https://github.com/user-attachments/assets/5d6b0801-75aa-4e04-9772-d885edefa8bf)

8. Plot of Id Vs Rd:

![Image](https://github.com/user-attachments/assets/0bc708e2-6e24-4c4d-bd88-d36361b45c91) 














