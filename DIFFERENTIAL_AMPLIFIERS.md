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





   

   



   












