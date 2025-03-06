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

NOTE : Differential Signals:
1. They vary by equal and opposite amounts.
2. They have same average (dc) value : the common mode level.

Where are these the Differential Amplifiers used then ? OP-AMPS and many more circuits.

GENERAL STRUCTURE OF MOS DIFFERENTIAL AMPLIFIER :

![Image](https://github.com/user-attachments/assets/7932856c-856c-4322-b239-030eada6354e)

Let's go through the General Properties :

1. When Common mode Input Voltage {Vcm,in} is being applied to both the MOSFETs:

   CIRCUIT :

![Image](https://github.com/user-attachments/assets/894143ec-d4cb-4fac-b606-3914f56d0520) 


   Here Vin1 = Vin2 , and thus the Differential pair is in "EQUILIBRIUM".As a result, current flows through the MOSFETS {Id1=Id2=Iss/2} from Supply {Vdd} through Drain resistances {Rd} and through mosfets and then getting joined to form current source ,Iss [Tail- Current] and to ground.

Since we are using the MOSFET in Saturation region, the current flowing is given by equation 

![Image](https://github.com/user-attachments/assets/74db5abd-b4ae-445f-ac8d-417cb080cf9f)  

Why Saturation ?

Higher transconductance and good Gain.


and Thus the output Voltage taken across Vx and Vy is Vx= Vy = Vdd - Rd*Iss/2 .
After rearranging the terms the Equilibrium Overdrive Voltage is given as :

![Image](https://github.com/user-attachments/assets/27b117fe-8b4b-4828-9cae-376804e4046e)

Q.If Vcm,in changes, what quantities in the circuit changes ? 

ANS : Nothing Changes.


2. Differential Behavior:

   CIRCUIT :

![Image](https://github.com/user-attachments/assets/68d85071-c834-441e-a3d3-544374dae114)


As the Vin is different (same dc and complimentary)

   Considering the plot of Id Vs Vin1-Vin2 its observed as follows:

   ![Image](https://github.com/user-attachments/assets/0f9df25e-6884-46b4-926a-4056f6378711) 


When  one of the input is given high , more drain current flows and Iss will hold that value and thus the other drain current of another MOSFET decreases and vice versa.When Vin1-Vin2 = 0 or Vin1=Vin2 then there is equal amounts of current flowing the drain current has the drain current value as Iss/2 as shown in the figure.

   Now considering the plot of Vx-Vy Vs Vin1-Vin2 its observed as follows:

   ![Image](https://github.com/user-attachments/assets/9ee0b51e-0d8e-44ec-9a83-717b2515a987)  

Vx-Vy is given by Vdd-Id1*Rd-(Vdd-Id2*Rd) = -Rd(Id1 - Id2) . Here negative because of inverting.

And thus for a particular high value of input voltage one of the MOSFET becomes ON and the other is OFF {END Conditions} and have values -Rd*Iss. Ex: if Id1 flows and Id2 is 0 then Iss = Id1.

Q. What is this minimum value of Vin-Vin2 at which one MOSFET turns OFF ?

ANS : Assume Vin1 > Vin2 , then the M1 conducts and M2 should be off orjust starting to get turn off, observing the Saturation current equation we observe that when Vgs = Vth this condition occurs, also the Vp is given by

From M1 : Vp = Vin1 - Vgs1
From M2 : Vp = Vgs2 = {Vth}

as shown below and ,thus substituting the values when get the below Equation:

![Image](https://github.com/user-attachments/assets/fadc499b-875b-41fc-8b1b-947a159ee9a3) 


LARGE SIGNAL ANALYSIS :

Lets now find out the equation for the plot of Vx-Vy Vs Vin1-Vin2 , from the above equations we have :

![Image](https://github.com/user-attachments/assets/9ee0b51e-0d8e-44ec-9a83-717b2515a987)


OBSERVATIONS :

1.Id1-Id2 = 0 when Vin1=Vin2 , but since we have the under-root term holding up 2 positive values, it possible that the square term becoming equal to 4Iss/(Un*Cox*W/L) leads the Id1-Id2 to become zero, something like this:

![Image](https://github.com/user-attachments/assets/b49fe525-b576-4243-8523-9f770f1f4bc1)

When terms inside square root becomes zero then,

![Image](https://github.com/user-attachments/assets/1ce42fdf-ec4d-4f4b-8225-401eb6bcda14) 


Thus the above equation is valid only if M1 and M2 are ON and at the edge of transistor turn OFF, and what is that up-to value of Vin1-Vin2 value that has this condtition ? (as stated earlier):WE know this is equal to Root(2) * Equilibrium Overdrive Voltage :


![Image](https://github.com/user-attachments/assets/fadc499b-875b-41fc-8b1b-947a159ee9a3) 


So thus, Minimum |Vin1-Vin2| to turn off one side = Root(2)*Equilibrium Overdrive Voltage

Now coming back to the original equation relating Vx-Vy with Vin1-Vin2, we observe that there is this square term leading to slight distortion , and to eliminate that we need to make sure that :

|Vin1-Vin2|^2 << 4Iss/(Un*Cox*W/L)





Q.What happens if Iss is doubled ?

Ans: Referring to the circuit below , the slope changes and it becomes more linear because it can take a larger input difference without "DYING".

![Image](https://github.com/user-attachments/assets/a54e673b-eba6-4084-9fb8-712895896268)  

Q. What happens if W/L is doubled ?

Ans : The circuit becomes less linear, because it can take only a smaller input difference before it "DIES".

![Image](https://github.com/user-attachments/assets/d51461c2-08a3-4d96-997e-5a8b271ccb14) 
-------------------------------------------------------------------------------------------------------------------------------------------------------------
Coming to the experiment and analysis.

Q. Design and analyze the differential amplifier for the following specifications.
Vdd = 1.8v , P <= 2.2mW , Vicm = 0.95v , Vocm = 1.1v , Vp = 0.4V.

To perform the DC Analysis,Transient Analysis, Frequency Response and to extract the parameters.

![Image](https://github.com/user-attachments/assets/07ba5c99-892f-4ed6-baad-54b4c2d58f73)

![Image](https://github.com/user-attachments/assets/344bffac-b9f0-4b58-8610-ebdce7c0ada4)


Based on the calculations { as shown above }

Iss = 1.222mA

Rss = 327.3322 Ohms

Id1 = Id2 = 0.611mA

Rd = 1.1456 Kilo Ohms


VARIOUS CIRCUITS:
-------------------------------------------------------------------------------------------------------------------------------------------------------------

[A] With Resistor Rss:

![Image](https://github.com/user-attachments/assets/5cfd20c5-c4ea-450f-bf1d-6a54aa890226)


ANALYSIS :
-------------------------------------------------------------------------------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):

![Image](https://github.com/user-attachments/assets/dcac2a8e-1076-4677-8d7c-dc0570cef815)  

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

![Image](https://github.com/user-attachments/assets/9422d152-7707-4dc1-b569-444c34314328) 


Q - point changes to (0.471931V,0.73mA).

-------------------------------------------------------------------------------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

![Image](https://github.com/user-attachments/assets/fd42cda6-179b-454e-88ec-3df15eef2ed4)

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

![Image](https://github.com/user-attachments/assets/332eb4a5-a6d3-40ad-abeb-9cabd98a1821) 

From graph , Gain(Av) = Vout_pp/Vin_pp = -5.3158

In terms of dB, Gain(dB) = 20*log(Av) = 20*log(5.3158) = 14.5113 dB

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

![Image](https://github.com/user-attachments/assets/f1773935-ec01-446d-87fd-05e6c5f7737f) 

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.32108V.

![Image](https://github.com/user-attachments/assets/9a1ad902-0704-4dbe-a910-8c6256eb0e45)



-------------------------------------------------------------------------------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in dB, by appling (-3dB) the gain will be 11.5113dB having the frequency at fH = 1.273Ghz and fL = 0, Thus B.W = fH - fL = 1.273Ghz.

![Image](https://github.com/user-attachments/assets/a630fe43-16b0-4040-9698-7c33b371390b) 






-------------------------------------------------------------------------------------------------------------------------------------------------------------
[B] With Current Source Iss:

![Image](https://github.com/user-attachments/assets/caf2007c-33cf-4ffd-94c0-cbe02342dd0f) 



ANALYSIS :
-------------------------------------------------------------------------------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):

![Image](https://github.com/user-attachments/assets/249836a9-f340-4dd1-a94a-91501cfaadd4) 

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

![Image](https://github.com/user-attachments/assets/01618b47-1b3a-415d-8101-c506f220d678)


Q - point changes to (0.581373V,0.63mA).

-------------------------------------------------------------------------------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

![Image](https://github.com/user-attachments/assets/ebecc9dc-9ffe-446b-ab93-6b05c4f9ae8a)

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

![Image](https://github.com/user-attachments/assets/78f57db7-b2b2-4ed2-a144-88719c2d7d7e) 

From graph , Gain(Av) = Vout_pp/Vin_pp = -4.609015

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

![Image](https://github.com/user-attachments/assets/e785df80-5dec-487e-9b08-58205addd87d)

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.265898V.

![Image](https://github.com/user-attachments/assets/ea2e347d-c358-4cd9-aa23-a795404dd257)



-------------------------------------------------------------------------------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in dB, by appling (-3dB) the gain will be 10.2721dB having the frequency at fH = 1.252Ghz and fL = 0, Thus B.W = fH - fL = 1.252Ghz.


![Image](https://github.com/user-attachments/assets/c3ac39e4-4a9a-4860-aac9-0279fce10646)




-------------------------------------------------------------------------------------------------------------------------------------------------------------
[C] With NMOS:

![Image](https://github.com/user-attachments/assets/1fdbd1cc-4f74-4828-a756-0c16420b14b5) 

ANALYSIS :
-------------------------------------------------------------------------------------------------------------------------------------------------------------
1.DC ANALYSIS - Fixing the Operating Point (Q-Point):

![Image](https://github.com/user-attachments/assets/8b602b9c-1709-450f-ac20-36b0c5c71ce8) 

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

For NMOS (used instead of Iss) :
Vb = 0.895V
W = 11.82u
L = 180n
VDS >= Vov : 0.4 >= (0.95V-0.4V)-0.495V = 0.4>= 0.055V {CONDITION SATISFIES FOR SATURATION}.  

*Slightly increasing the Vcm,in from 0.95V to 1.05V (0.1V increase), then

![Image](https://github.com/user-attachments/assets/d196cbc7-5938-4a93-9497-e63702de0864)


Q - point changes to (0.581373V,0.631mA).

-------------------------------------------------------------------------------------------------------------------------------------------------------------
2. TRANSIENT ANALYSIS - Finding the maximum input and output swing

CIRCUIT & WAVEFORMS -

![Image](https://github.com/user-attachments/assets/e07db326-f4f1-483b-b343-5c3d7f5f5111)  

We thus observe an 180 deg phase shift in output signal and output voltage being amplified.

From graph , Gain(Av) = Vout_pp/Vin_pp = -4.77496

In terms of dB, Gain(dB) = 20*log(Av) = 20*log(4.77496) = 13.5793 dB

Overall gain using Small signal model is given by Av = Gm * Rd, gm = 2*Id/Vov = (2*0.611mA)/(0.95-0.495) = 2.68m

Rout = Rd = 1.1456 Kilo Ohms

Thus, Av = 2.68m * 1.1456 K = 3.07675


![Image](https://github.com/user-attachments/assets/8cff4f70-f4a6-4738-8b07-9335caf807be) 

To Calculate, 

Vcm,in_min = Vtn + Vp = 0.495V + 0.4V = 0.895V

Vcm,in_max = Vdd - (Iss/2)*Rd + Vtn = 1.8v-(1.222mA/2)* 1.1456K + 0.495V = 1.5950384V.

Vcm,in = (Vin,cm_min + Vin,cm_max)/2 = 1.245V

Similarly,

Vocm_min = Vov + Vp = (0.95V-0.495V) + 0.4V = 0.855V

Vocm_max = Vdd - ID*Rd = 1.8V - (0.611mA)*1.1456k = 1.1000384V.

Vocm = (Vocm_min + Vocm_max)/2 = 0.9775V.

![Image](https://github.com/user-attachments/assets/a71e585c-f63a-43a4-872a-f66d76b1a93d) 

By applying DC offset Voltage of 1.2V and 500mV input amplitude {1.7V} , we observed the output to be clipped and whose value Vo_pp given by 1.2838 V.

![Image](https://github.com/user-attachments/assets/855b94e2-83a4-4de0-9ef3-c13bd20b36ed) 



-------------------------------------------------------------------------------------------------------------------------------------------------------------
3. AC ANALYSIS - Finding the Bandwidth

The below figure shows the Gain of the circuit in 13.5793dB, by appling (-3dB) the gain will be  10.5793 dB having the frequency at fH = 1.477Ghz and fL = 0, Thus B.W = fH - fL = 1.477 Ghz.


![Image](https://github.com/user-attachments/assets/8e9b6067-d79c-42a0-b771-33cbe3e03cc6)




-------------------------------------------------------------------------------------------------------------------------------------------------------------

INFERENCE / SUMMARY :

1. Noise Rejection (Common-Mode Rejection): Differential amplifiers effectively remove common-mode noise, making them ideal for applications like ECG signal amplification where low-level signals need to be extracted from noisy environments.

2. Operating in Saturation Region: The MOSFETs in the differential pair must remain in saturation to ensure high transconductance and gain. This is verified by the conditions VDS >= Vov.

3. Gain Characteristics: The voltage gain of the designed amplifier was approximately -5.3158 V/V (14.51 dB), which aligns with the small-signal model prediction  Av = gm*Rd.

4. Common-Mode Input and Output Range: The common-mode input voltage range was found to be 0.895V to 1.595V, while the common-mode output voltage range was 0.855V to 1.100V, defining the operational limits.

5. Large Signal Behavior: The circuit exhibits 180° phase shift between input and output, confirming inverting behavior. Beyond certain input limits, the output clips due to saturation effects.

6. Effect of Increasing Iss or W/L: Increasing Iss improves linearity, allowing for a wider input range, while increasing W/L reduces linearity, limiting the acceptable input range before transistor cut-off occurs.
   
7. Note that the AC / Transient Analysis we have applied an input AC Voltage is given at only one end.This helps to better analyse the analysis part. However adding the 180 deg phase shift signal to other end increases the gain as the difference of these 2 signals increases.

8. Also we need to need observe that the 'BODY-EFFECT' plays a role here , and thus we know that it increases the threshold voltage thus we are using Vtn = 0.497V and not Vth = 0.366V.

   TABULAR_COLUMN:

   
    

   

   



   












