PART A)

Q.Design and analyze current mirror circuit as active load in amplifier circuit , which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and  P <= 1mW. Perform DC and AC analysis for mirror ratio 1:1, 1:2. Vary length from 180nm , 500nm , 1µm.

We know that, 

Itotal = P/Vdd = 1mW/1.8V = 0.555 mA

Iref = Id = Itotal/2 = 0.555mA/2 = 0.277 mA

To find Vin , Av = -gm * Rout = -gm *(ro1||r02) .

ro1=1/lambda1*(Id1) ; ro2 = 1/lambda2*(Id2) ; Here Id1 = Id2 = Id.

Thus Av= -gm * {(1)/Id*(lambda1 + lambda2)} ; here gm = 2Id/Vov

and thus substituting in equation we get Av = 2/Vov(lambda1+lambda2) ;

Vov = 0.073V and thus Vgs = 0.073 + 0.496 == 0.569V. 

As Source is grounded , Vs = 0v and thus Vg = Vgs = 0.569V.

In General, 1:1 using ratio , then Iref = 0.277mA.
For 1:2 using ration, then Iref = Itotal/3 = 0.183mA.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


CIRCUIT 1: 1:1 using 180nm

A. DC Analysis: 

![Image](https://github.com/user-attachments/assets/3620b47a-b940-4d92-8df2-1506af65c59b) 


![Image](https://github.com/user-attachments/assets/7a7b489e-b157-4077-996c-525d1b1d3bc1)

B. Transient Analysis :

![Image](https://github.com/user-attachments/assets/45d8c249-66c9-44a2-a9e3-d06648bccabe)

![Image](https://github.com/user-attachments/assets/350502e5-6fce-41fd-bedb-03b682929771)

C. Frequency Response :

![Image](https://github.com/user-attachments/assets/b187968d-415f-4813-8c7e-058b63819a22) 

![Image](https://github.com/user-attachments/assets/3360252b-e857-422a-bb0c-2f8ce78940e6)

Bandwidth is 207.218Mhz.(30dB-3dB= 27dB)

(W,L) for CMOSP is 10u,180nm and for CMOSN is 31.23u,180n.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


CIRCUIT 2: 1:2 using 180nm

A. DC Analysis:

![Image](https://github.com/user-attachments/assets/5f2b07e6-2a7e-442c-bb44-213e29d4f64d) 

![Image](https://github.com/user-attachments/assets/5963549e-77d6-493b-a401-5c0075c25d3d) 

B. Transient Analysis :

![Image](https://github.com/user-attachments/assets/e8db7697-1092-45c2-bd48-16069fa9d5cd) 

![Image](https://github.com/user-attachments/assets/86d898d8-486a-443b-94f6-2d47cac5347c) 

C. Frequency Response :

![Image](https://github.com/user-attachments/assets/f38e6a20-b7a0-4dc8-84bf-a4b3d31676df)

![Image](https://github.com/user-attachments/assets/fe655a6d-6e02-434b-9d89-359fd16cd341) 

Bandwidth is 139.454Mhz.(30dB-3dB = 27dB )

(W.L) for CMOSP1 is 10u,180n & (W,L) for CMOSP2 is 20u,180n & (W,L) for CMOSN is 41.127u,180n.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CIRCUIT 3 : 1:1 using 500nm

A. DC Analysis :

![Image](https://github.com/user-attachments/assets/b99511c9-4006-4018-82f3-968651e200ff)

![Image](https://github.com/user-attachments/assets/f0a6006c-cf19-46b6-8b20-275f3f1e84b9)  


B. Transient Analysis :


![Image](https://github.com/user-attachments/assets/ade0c0f8-77b0-469f-af74-6ebf7c5f97ff)

![Image](https://github.com/user-attachments/assets/f7e593c6-7004-4ee6-a953-ace25352489f)


C. Frequency Response :

![Image](https://github.com/user-attachments/assets/c586a526-65fa-445f-88c5-5d326068f926) 

![Image](https://github.com/user-attachments/assets/a16f98d1-eb76-4c3d-9c4d-c3bece7af707)



(W,L) for CMOSP is 10u,500nm and for CMOSN is 65.19u,500n.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


CIRCUIT 4: 1:2 using 500nm

A. DC Analysis :


![Image](https://github.com/user-attachments/assets/3cef16a2-b6a0-484e-bf31-02ac5ffd3ac0) 


![Image](https://github.com/user-attachments/assets/706ab9e7-d28b-48c6-9deb-011c513e141f)


B. Transient Analysis :

![Image](https://github.com/user-attachments/assets/2bf5b5e7-49bf-47f7-9bea-0b01efa8ab9e)


![Image](https://github.com/user-attachments/assets/ccf20e64-3242-414e-84f4-310532fb189b)



C. Frequency Response :

![Image](https://github.com/user-attachments/assets/6a10e53c-8358-430d-984e-9e17f0b13fdb)


![Image](https://github.com/user-attachments/assets/ece0c6a0-4410-40d3-ba05-2ab132b2a03e)

Bandwidth is 26.778Mhz.(39dB-3dB = 36dB ).

(W.L) for CMOSP1 is 10u,500n & (W,L) for CMOSP2 is 20u,500n & (W,L) for CMOSN is 85.243u,500n.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


CIRCUIT 5: 1:1 using 1um

A. DC Analysis :

![Image](https://github.com/user-attachments/assets/ae6ced4a-81fb-487a-af96-055d8b8fa4c2) 


![Image](https://github.com/user-attachments/assets/fbd115b1-9c7a-4fdd-8ead-bd33d439564d) 


B. Transient Analysis :

![Image](https://github.com/user-attachments/assets/7bbcde80-d5be-4f3c-9210-3a7a7e6aba78)


![Image](https://github.com/user-attachments/assets/a7447680-13e7-4956-985b-30ac8a989161)


C. Frequency Response :


![Image](https://github.com/user-attachments/assets/2fd29ef0-e8f2-4c6d-aee6-48067874affd) 


![Image](https://github.com/user-attachments/assets/05ce7928-eb6e-409d-b64e-3562964762e8)  

Bnadwidth is 37.249Mhz.(36dB-3dB= 33dB ).

(W,L) for CMOSP is 10u,1um and for CMOSN is 93.35u,1u.
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CIRCUIT 6: 1:2 using 1um

A. DC Analysis :

![Image](https://github.com/user-attachments/assets/328bd1f1-58e7-4cfe-b9ff-6062c5ecb81f) 

![Image](https://github.com/user-attachments/assets/a36a42a8-5b42-4591-a2df-0fee5ae44fa2) 


B. Transient Analysis :


![Image](https://github.com/user-attachments/assets/d5b58fb8-63b5-4759-add5-a204fa32373c)


![Image](https://github.com/user-attachments/assets/cc5e0063-0dca-4fb9-8c12-6a0b34ad05ad)  


C. Frequency Response :


![Image](https://github.com/user-attachments/assets/b75d5336-ad57-4d49-8d77-67f9a4c9a724) 


![Image](https://github.com/user-attachments/assets/6ecaf4af-ffaf-402c-a8a9-d7699c91b0b0)

Bandwidth is 18.321Mhz.(39dB-3dB = 36dB ).


(W.L) for CMOSP1 is 10u,1u & (W,L) for CMOSP2 is 20u,1u & (W,L) for CMOSN is 121.51u,1u.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


PART B) DIFFERENTIAL AMPLIFIERS

CIRCUIT :




DC OPERATING POINT :














