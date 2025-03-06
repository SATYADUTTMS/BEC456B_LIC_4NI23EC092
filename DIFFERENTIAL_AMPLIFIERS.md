AIM : This Experiment is on the Analysis and Design of Differential Amplifiers.

First of all , What are Differential Amplifiers ? Why do we use and where do we use ?

THEORY:

Let's start of by considering an example . Consider an ElectroCardiogram System {ECG} , which is a system that measures the internal body components and displays on an electronic deviee. We know that these signals are in order of millivolts and needs to be amplified using Amplifier. OK Fine, we can use a CS Amplifier and increase the signal and provide to the device such that it can viewed easily and analyzed.

Now here is the catch, since we are dealing with Analog Electronics , there is this another supreme Contender, namely the 'NOISE'. We know that Noise is an unwanted distortions in our signals that poses a lot of issues.These come from the surroundings imposing on the wires or from sources connected and others....

So when we amplify the signal ,these noise signals wil also get amplified. Thus there is a ''PROBLEM OF NOISE COUPLING''. Inorder to remove this we design a circuit such that the Noise gets removed, namely the Difference Ampilifers. In our example the signal is taken from both sides and applied to an Amplifer {Op-AMP} in our case and the difference of these signals getting amplified and thus Noise becoming to both gets removed easily. How ?

Noise is being ''Common'' to both the nodes and thus we can assume as Common input voltage which is exactly the same for both the nodes.

Thus at pin 2 = V1(signal) : Vcm(noise) + Vin1(actual signal)

Similarly at pin 3 = V2(signal) : Vcm(noise) + Vin2(actual signal)

and thus considering the difference of these V1 - V2 = Vin1 - Vin2 and thus Vout = Ad * Vin , where Vin = Vin1 - Vin2. And thus the definition, the difference of the input signals getting amplified by a factor Ad is what it gives the output.

Thus the pictorial representation is as follows :



NOTE : Differential Signals:
1. They vary by equal and opposite amounts.
2. They have same average (dc) value : the common mode level.

Where are these the Differential Amplifiers used then ? OP-AMPS and many more circuits.

Example (OP-AMP):




GENERAL STRUCTURE OF MOS DIFFERENTIAL AMPLIFIER :



Let's go through the General Properties :

1. When Common mode Input Voltage {Vcm,in} is being applied to both the MOSFETs:

   CIRCUIT :



   Here Vin1 = Vin2 , and thus the Differential pair is in "EQUILIBRIUM".As a result, current flows through the MOSFETS {Id1=Id2=Iss/2} from Supply {Vdd} through Drain resistances {Rd} and through mosfets and then getting joined to form current source ,Iss [Tail- Current] and to ground.

Since we are using the MOSFET in Saturation region, the current flowing is given by equation 


Why Saturation ?

Higher transconductance and good Gain.


and Thus the output Voltage taken across Vx and Vy is Vx= Vy = Vdd - Rd*Iss/2 .
After rearranging the terms Vgs is given by


and Similary the Equilibrium Overdrive Voltage as :



Q.If Vcm,in changes, what quantities in the circuit changes ? 

ANS : Nothing Changes.


2. Differential Behavior:

   CIRCUIT :



As the Vin is different (same dc and complimentary)

   Considering the plot of Id Vs Vin1-Vin2 its observed as follows:


When  one of the input is given high , more drain current flows and Iss will hold that value and thus the other drain current of another MOSFET decreases and vice versa.When Vin1-Vin2 = 0 or Vin1=Vin2 then there is equal amounts of current flowing the drain current has the drain current value as Iss/2 as shown in the figure.

   Now considering the plot of Vx-Vy Vs Vin1-Vin2 its observed as follows:

Vx-Vy is given by Vdd-Id1*Rd-(Vdd-Id2*Rd) = -Rd(Id1 - Id2) . Here negative because of inverting.

And thus for a particular high value of input voltage one of the MOSFET becomes ON and the other is OFF {END Conditions} and have values -Rd*Iss. Ex: if Id1 flows and Id2 is 0 then Iss = Id1.

Q. Whatis this minimum value of Vin-Vin2 at which one MOSFET turns OFF ?

ANS : Assume Vin1 > Vin2 , then the M1 conducts and M2 should be off orjust starting to get turn off, observing the Saturation current equation we observe that when Vgs = Vth this condition occurs, also the Vp is given by

From M1 : Vp = Vin1 - Vgs1
From M2 : Vp = Vgs2 = {Vth}

as shown below and ,thus substituting the values when get the below Equation:




LARGE SIGNAL ANALYSIS :

Lets now find out the equation for the plot of Vx-Vy Vs Vin1-Vin2 , from the above equations we have :




OBSERVATIONS :

1.Id1-Id2 = 0 when Vin1=Vin2 , but since we have the under-root term holding up 2 positive values, it possible that the square term becoming equal to 4Iss/(Un*Cox*W/L) leads the Id1-Id2 to become zero, something like this:


Thus the above equation is valid only if M1 and M2 are ON and at the edge of transistor turn OFF, and what is that up-to value of Vin1-Vin2 value that has this condtition ? (as stated earlier):




WE know this is equal to Root(2) * Equilibrium Overdrive Voltage :


So thus, Minimum |Vin1-Vin2| to turn off one side = Root(2)*Equilibrium Overdrive Voltage

Now coming back to the original equation relating Vx-Vy with Vin1-Vin2, we observe that there is this square term leading to slight distortion , and to eliminate that we need to make sure that :

|Vin1-Vin2|^2 << 4Iss/(Un*Cox*W/L)

Such that :

Slope{ GAIN } is given by : 

Q.What happens if Iss is doubled ?

Ans: Referring to the circuit below , the slope changes and it becomes more linear because it can take a larger input difference without "DYING".



Q. What happens if W/L is doubled ?

Ans : The circuit becomes less linear, because it can take only a smaller input difference before it "DIES".

-----------------------------------------------------------------------------------------
Coming to the experiment and analysis.

Q. Design and analyze the differential amplifier for the following specifications.
Vdd = 1.8v , P <= 2.2mW , Vicm = 0.95v , Vocm = 1.1v , Vp = 0.4V.

To perform the DC Analysis,Transient Analysis, Frequency Response and to extract the parameters.




Based on the calculations { as shown above }

Iss = 1.222mA

Rss = 327.3322 Ohms

Id1 = Id2 = 0.611mA

Rd = 1.1456 Kilo Ohms


VARIOUS CIRCUITS:
-----------------------------------------------------------------------------------------

[A] With Resistor Rss:



ANALYSIS :
-----------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):


Length (M1 and M2) = L = 180n

Width (M1 and M2) = W = 108.3u

MOSFET M1 :

Vcm,in = 0.95V

Vocm1 = 1.100V

Id1 = 0.611mA

Vtn = 0.495V

VGS = 0.95 - 0.4 = 0.55V

From the figure , Vdd = IdRd + VDS + Vp

thus, VDS = 1.8 - 0.699 - 0.4 = 0.701v

Similarly for MOSFET M2 as they are perfectly matched and are symmetric.

To verify the Saturation Conditions :
VGD <= Vtn

(0.95V-1.1V) <= 0.495V

-0.15V <= 0.495V {CONDITION SATISFIES}

Also

VDS >= Vov

(1.1V-0.4V) >= VGS - Vtn

(1.1V-0.4V) >= (0.95V-0.4V) - 0.495V

0.7V >= 0.055V {CONDITION SATISFIES}

Hence, we can say that the MOSFETS are in SATURATION REGION.

Q-POINT = (0.7V,0.611mA)

*Slightly increasing the Vcm,in from 0.95V to 1.05V (0.1V increase), then


Q - point changes to (0.471931V,0.73mA).

-----------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

From graph , Gain(Av) = Vout_pp/Vin_pp = 

In terms of dB, Gain(dB) = 20*log(Av) = 20*log(5.4095) = 14.6631 dB

Overall gain using Small signal model is given by Av = Gm * Rd, gm = 2*Id/Vov = (2*0.611mA)/(0.95-0.495) = 2.685m

Rout = Rd = 1.1456 Kilo Ohms

Thus, Av = 2.685m * 1.1456 K = 3.075 V/V.


To Calculate, 

Vcm,in_min = Vtn + Vp = 0.495V + 0.4V = 0.895V

Vcm,in_max = Vdd - (Iss/2)*Rd + Vtn = 1.8v-(1.222mA/2)* 1.1456K + 0.495V = 1.5950384V.

Vcm,in = (Vin,cm_min + Vin,cm_max)/2 = 1.245V

Similarly,

Vocm_min = Vov + Vp = (0.95V-0.495V) + 0.4V = 0.855V

Vocm_max = Vdd - ID*Rd = 1.8V - (0.611mA)*1.1456k = 1.1000384V.

Vocm = (Vocm_min + Vocm_max)/2 = 0.9775V.

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.32108V.



-----------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in dB, by appling (-3dB) the gain will be 11.663dB having the frequency at fH = 1.273Ghz and fL = 0, Thus B.W = fH - fL = 1.273Ghz.






-----------------------------------------------------------------------------------------------
[C] With NMOS:



ANALYSIS :
-----------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):


Length (M1 and M2) = L = 180n

Width (M1 and M2) = W = 108.3u

MOSFET M1 :

Vcm,in = 0.95V

Vocm1 = 1.100V

Id1 = 0.611mA

Vtn = 0.495V

VGS = 0.95 - 0.4 = 0.55V

From the figure , Vdd = IdRd + VDS + Vp

thus, VDS = 1.8 - 0.699 - 0.4 = 0.701v

Similarly for MOSFET M2 as they are perfectly matched and are symmetric.

To verify the Saturation Conditions :
VGD <= Vtn

(0.95V-1.1V) <= 0.495V

-0.15V <= 0.495V {CONDITION SATISFIES}

Also

VDS >= Vov

(1.1V-0.4V) >= VGS - Vtn

(1.1V-0.4V) >= (0.95V-0.4V) - 0.495V

0.7V >= 0.055V {CONDITION SATISFIES}

Hence, we can say that the MOSFETS are in SATURATION REGION.

Q-POINT = (0.7V,0.611mA)

*Slightly increasing the Vcm,in from 0.95V to 1.05V (0.1V increase), then


Q - point changes to (0.581373V,0.63mA).

-----------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

From graph , Gain(Av) = Vout_pp/Vin_pp = 4.609015

In terms of dB, Gain(dB) = 20*log(Av) = 20*log(5.4095) = 13.2721 dB

Overall gain using Small signal model is given by Av = Gm * Rd, gm = 2*Id/Vov = (2*0.611mA)/(0.95-0.495) = 2.68m

Rout = Rd = 1.1456 Kilo Ohms

Thus, Av = 2.68m * 1.1456 K = 3.07675


To Calculate, 

Vcm,in_min = Vtn + Vp = 0.495V + 0.4V = 0.895V

Vcm,in_max = Vdd - (Iss/2)*Rd + Vtn = 1.8v-(1.222mA/2)* 1.1456K + 0.495V = 1.5950384V.

Vcm,in = (Vin,cm_min + Vin,cm_max)/2 = 1.245V

Similarly,

Vocm_min = Vov + Vp = (0.95V-0.495V) + 0.4V = 0.855V

Vocm_max = Vdd - ID*Rd = 1.8V - (0.611mA)*1.1456k = 1.1000384V.

Vocm = (Vocm_min + Vocm_max)/2 = 0.9775V.

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.265898V.



-----------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in dB, by appling (-3dB) the gain will be 10.2721dB having the frequency at fH = 1.252Ghz and fL = 0, Thus B.W = fH - fL = 1.252Ghz.







----------------------------------------------------------------------------------------------
[B] With Current Source Iss:



ANALYSIS :
-----------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):


Length (M1 and M2) = L = 180n

Width (M1 and M2) = W = 108.3u

MOSFET M1 :

Vcm,in = 0.95V

Vocm1 = 1.100V

Id1 = 0.611mA

Vtn = 0.495V

VGS = 0.95 - 0.4 = 0.55V

From the figure , Vdd = IdRd + VDS + Vp

thus, VDS = 1.8 - 0.699 - 0.4 = 0.701v

Similarly for MOSFET M2 as they are perfectly matched and are symmetric.

To verify the Saturation Conditions :
VGD <= Vtn

(0.95V-1.1V) <= 0.495V

-0.15V <= 0.495V {CONDITION SATISFIES}

Also

VDS >= Vov

(1.1V-0.4V) >= VGS - Vtn

(1.1V-0.4V) >= (0.95V-0.4V) - 0.495V

0.7V >= 0.055V {CONDITION SATISFIES}

Hence, we can say that the MOSFETS are in SATURATION REGION.

Q-POINT = (0.7V,0.611mA)

*Slightly increasing the Vcm,in from 0.95V to 1.05V (0.1V increase), then


Q - point changes to (0.581373V,0.63mA).

-----------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

From graph , Gain(Av) = Vout_pp/Vin_pp = 4.609015

In terms of dB, Gain(dB) = 20*log(Av) = 20*log(5.4095) = 13.2721 dB

Overall gain using Small signal model is given by Av = Gm * Rd, gm = 2*Id/Vov = (2*0.611mA)/(0.95-0.495) = 2.68m

Rout = Rd = 1.1456 Kilo Ohms

Thus, Av = 2.68m * 1.1456 K = 3.07675


To Calculate, 

Vcm,in_min = Vtn + Vp = 0.495V + 0.4V = 0.895V

Vcm,in_max = Vdd - (Iss/2)*Rd + Vtn = 1.8v-(1.222mA/2)* 1.1456K + 0.495V = 1.5950384V.

Vcm,in = (Vin,cm_min + Vin,cm_max)/2 = 1.245V

Similarly,

Vocm_min = Vov + Vp = (0.95V-0.495V) + 0.4V = 0.855V

Vocm_max = Vdd - ID*Rd = 1.8V - (0.611mA)*1.1456k = 1.1000384V.

Vocm = (Vocm_min + Vocm_max)/2 = 0.9775V.

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.265898V.



-----------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in dB, by appling (-3dB) the gain will be 10.2721dB having the frequency at fH = 1.252Ghz and fL = 0, Thus B.W = fH - fL = 1.252Ghz.







----------------------------------------------------------------------------------------------


   

   



   












