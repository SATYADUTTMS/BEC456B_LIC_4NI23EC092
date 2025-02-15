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

Its observed that when Vgs < Vth, the MOSFET is OFF , as a result Vds = Vdd. However When Vgs > Vth the MOSFET is ON , and if Vds >= Vov it works in Saturation Region (as required). Also if Vds < Vov the MOSFET works in Ohmic Region.

Now, why do we need Saturation Region ? If observed in the figure we get to know that the curve becomes almost linear in the saturation region. In an input is applied to this region the amplification is at maximum ( higher gain ). So this almost-linear region plays an important role during setting the Q-point.

An 180 deg phase shift is observed at the output. We observe that 







