Design and analyze current mirror circuit as active load in amplifier circuit , which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and  P <= 1mW. Perform DC and AC analysis for mirror ratio 1:1, 1:2. Vary length from 180nm , 500nm , 1µm.

We know that, 

Itotal = P/Vdd = 1mW/1.8V = 0.555 mA

Iref = Id = Itotal/2 = 0.555mA/2 = 0.2775 mA

To find Vin , Av = -gm * Rout = -gm *(ro1||r02) .

ro1=1/lambda1*(Id1) ; ro2 = 1/lambda2*(Id2) ; Here Id1 = Id2 = Id.

Thus Av= -gm * {(1)/Id*(lambda1 + lambda2)} ; here gm = 2Id/Vov

and thus substituting in equation we get Av = 2/Vov(lambda1+lambda2) ;

Vov = 0.073V and thus Vgs = 0.073 + 0.496 == 0.569V. 

As Source is grounded , Vs = 0v and thus Vg = Vgs = 0.569V.



ALL THE CIRCUITS, SIMULATIONS HAS BEEN PERFORMED, DOCUMENTATION WILL BE FINISHED EARLY.



