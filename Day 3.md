## VTC - SPICE simulation 
### Spice Deck
  
* component connectivity {netlist}

* PMOS :-

  ![Screenshot 2024-03-28 164130](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f41867c6-91d2-4958-947e-f43272acdcbc)

                                                                                                                                                                   -VSD-IAT

* NMOS :-

  ![Screenshot 2024-03-28 164136](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f0c88b9f-d0bf-4030-a39b-01c6ac133db7)

                                                                                                                                                                   -VSD-IAT

* Component value

  Like :-

  ![Screenshot 2024-03-28 164450](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/81b3bebb-b7b5-46b2-bd4d-1026268cd5ab)

                                                                                                                                                                   -VSD-IAT

* Identify nodes

  nodes :- a gate in between two objects.The object is the node.

  ![Screenshot 2024-03-28 164645](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a9c9c4aa-1795-44bb-8097-d90896ae581b)

                                                                                                                                                                    -VSD-IAT

* name the nodes

  ![Screenshot 2024-03-28 165024](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/48f57bd1-2d6a-489f-9b92-d0233479ec21)

                                                                                                                                                                    -VSD-IAT

### *** Model Description ***
### *** Netlist Description ***

* M1 out in vdd pmos W=0.375U
  
                     L=0.25U

* M2 out in 00 nmos W=0.375U

                    L=0.25U
 
* Cloud out 0 10f

  Vdd vdd 02.5

  Vin in 02.5


### Simulation Commands
 
*     .op

*    .dc vin 02.5  0.05

### *** include tsmc_025um_modes1.mod***
 
 *   LTB -"tsmc_025um_modes1.mod"

 *   CMOS_MODEIS.end


#### eg - 1 = SPICE waveform : Wn - Wp=0.375u,Ln,p=0.25u device (Wn/Ln=Wp/Lp=1.5)
 
    ![Screenshot 2024-03-28 171031](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9011f0ab-798c-4b12-97a9-56bd1128c992)



#### eg - 2 =   SPICE waveform : Wn=0.375,Wp=0.9375u,Ln,p=0.25u device (Wn/Ln=1.5,Wp/Lp=2.5)

  ![Screenshot 2024-03-28 171320](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/14a5abba-a6e9-4c6d-9ffd-8a876024295a)


  
### Difference between eg1 and eg2

*  we can see that eg1 is little to left and eg2 is middle

*   this show that the CMOS is Robustness
  
*  Static behaviour evaluation : CMOS invertor Robustness, Switching threshold,Vm

* Switching threshold is the point switches

*  Vm is a point where Vin=Vout

*  eg 1 =

  ![Screenshot 2024-03-28 224645](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3fe8cd74-a109-4cc0-addc-71f5a32f1540)

                                                                                                                                                                    -VSD-IAT
    
* eg 2 = 

 <img width="261" alt="eg 1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c782984f-ac94-439c-b0f1-3872b831c798">

                                                                                                                                                                   -VSD-IAT

* Vm = 

 <img width="535" alt="all" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4a6e05f8-1562-48f4-b1b5-da1b2a597681">

                                                                                                                                                                   -VSD-IAT

* Then in eg1 vgs = vds 

 ![Screenshot 2024-03-28 175340](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9731518f-90e8-4133-b914-a8156a2444bd)

                                                                                                                                                                    -VSD-IAT

## equations:

* Vm=R.Vdd/(1+R)

* R=KbVdsatp/KnVdsatn = (w/p)Kp1.Vdsatp/(Wn/Ln)Kn1.Vdsatp

                   Kn.Vdsatn(Vm-Vt)-Vdsatn/2
* (Wp/Lp)/(Wn/Ln) = ________________________________
                   Kbl.Vdsatb(-Vm+Vdd+Vt)+VdsatB/2


## 16-mask CMOS process
### selecting a substrate

  will take a normal block

  ![Screenshot 2024-03-28 193231](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68c2ceb3-d415-4fb4-97a2-bf52bd08b0da)

                                                                                                                                                                    -VSD-IAT

called P-substrate
### Creating a active region for transistors

*  Create isolation between all substrate

*  Mask1 is the layout with layers

  ![Screenshot 2024-03-28 194206](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ef292f21-1ecc-4f5c-8873-42d27fe6e2c0)

                                                                                                                                                                    -VSD-IAT

* poto washed away

 <img width="494" alt="e" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/be97bdb1-c7ad-45bd-af75-429f25aa8145">

                                                                                                                                                                   -VSD-IAT

* chemically removed

 ![Screenshot 2024-03-28 194810](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/888e6b08-4681-46c4-928e-b6014ed6260d)

                                                                                                                                                                   -VSD-IAT

* Bird's breack

 <img width="593" alt="r" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d7626e44-074b-4e61-8cf2-63f8f85b1ea4">

                                                                                                                                                                    -VSD-IAT

### N-well and P-well formation

* Mask look like

  <img width="600" alt="l" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6b087dc3-d57d-492a-b455-67fa69d781e7">

                                                                                                                                                                    -VSD-IAT

* Layers

  ![Screenshot 2024-03-28 195258](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/da375175-bb75-4cee-a1cb-42603e97df4c)

                                                                                                                                                                    -VSD-IAT

* then implement P-MOS like this

  ![Screenshot 2024-03-28 195538](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/208789ea-1232-4495-9c92-10bfb673d840)

                                                                                                                                                                    -VSD-IAT

*  then implement N-MOS like this

  ![Screenshot 2024-03-28 195731](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/178694c4-ac82-4d30-8421-c3f3845546b9)

                                                                                                                                                                    -VSD-IAT

*  In the last we can see this

  ![Screenshot 2024-03-28 200626](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9e07e02d-9aa9-4234-9d29-3bda8ef999f9)

                                                                                                                                                                    -VSD-IAT

*  to expand P,N MOSS we put it in high temperature

  <img width="475" alt="k" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/248e764e-727a-4b76-a37a-4bd8b004f5cc">

                                                                                                                                                                    -VSD-IAT

### Formation of "gate"

*  for creating douping concentration in PMOS

  ![Screenshot 2024-03-28 200626](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/de76fc05-731f-4902-8c70-1eadc2e4556a)

                                                                                                                                                                    -VSD-IAT

*  for creating douping concentration in NMOS

  ![Screenshot 2024-03-28 200838](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bc095e15-e7da-4210-9f38-84e0d289a690)

                                                                                                                                                                    -VSD-IAT

* As the oxide is damaged originally, so the oxide is etched usin dilute hydroflouric acid{HF}

![Screenshot 2024-03-28 202240](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68ecab63-006d-4f79-a58d-d1598db56fee)

                                                                                                                                                                    -VSD-IAT

* Then regrow it again {10n thin}to put in the gates,first we put many layers

<img width="431" alt="h" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1f296214-b6c9-4859-b956-f45d77bf448e">

                                                                                                                                                                    -VSD-IAT

* by UV light the layers are eched away

![Screenshot 2024-03-28 203325](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/5b33ace0-4874-4565-9da1-4a00830130e8)

                                                                                                                                                                    -VSD-IAT

* In the last this is the gate we get

![Screenshot 2024-03-28 203401](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/536d63f7-68f5-4c60-8d56-f38fa6a43f60)

                                                                                                                                                                    -VSD-IAT

### Lihtly Doped Drain{LDD} formation

* while fabricating in NMOS in P-well, we get source and drain and they both are P type, which is P+

  P-  is the LDD

  N is N well

  So we have 3types of doping for NMOS - P+, P-, N

* Here source and drain are N

  N- is LDD

  P is P-well

  So we have 3 types of doping for PMOS - N+,N-, P

 ### Why we need these all

 * there are 2 reasons for this

    Hot electron effect

    Short channel effect

  * Hot Electronic effect
 
    electronic fold  E=V/d

    High Energy carriers break si-si bonds

    3.2.v barrier between Si conduction band

    SiO2 conduction band

### Short channel effeft
 * For short channel, drain field penetrates as channel

### process for implant

  ![Screenshot 2024-03-28 210634](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d8451a4c-0de5-4895-90ca-8e42d58f907e)

                                                                                                                                                                    -VSD-IAT

  👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇

  ![image](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1eb940e5-99c8-4e8d-a096-40c1c8b45475)

                                                                                                                                                                    -VSD-IAT
 
 * To protect the implemented N,P we use SiO2. Then Plasma anisotropic etches it. some side wall spaces are created protects.

### Source and drain formation

 * To make N+ in P-wall

  ![Screenshot 2024-03-28 211005](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ca0f34d4-09cb-4e8b-bb04-7588c4b5617d)

                                                                                                                                                                    -VSD-IAT

*  To Make P+ in N-wall
 
  <img width="417" alt="p1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a5b0078f-1619-4381-af16-f2b84589c5d8">

                                                                                                                                                                    -VSD-IAT

*  then in high temperature

![Screenshot 2024-03-28 211615](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/85209953-9143-439d-84c5-8674a226fcfe)

                                                                                                                                                                    -VSD-IAT

### mask-16 process continuation

*  etch thin oxide in HF solution

  <img width="400" alt="m" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/b7e5a5c5-a23f-4456-90f9-d2dbe87e596f">

                                                                                                                                                                    -VSD-IAT

* deposit titanium on water surface,using sputtering

*  sputtering means we have to take titanium metal and hit it with Argon gas

*  for this the particles of titanium metal will be spited out and deposited on the substrate.

*  after depositing the titanium metal

  <img width="408" alt="m1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6177968f-7577-4c1d-b04c-c5cd2ace3244">

                                                                                                                                                                    -VSD-IAT

* then we have to heat it and the resultant we get is titanium silicon

  <img width="507" alt="m2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f36ffcff-9288-4292-bb84-71a3c8efefe6">

                                                                                                                                                                    -VSD-IAT

*  To bring the gates out we have to again do the same process with mask-11

  <img width="410" alt="m3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/50da90e6-42d1-48c7-b392-048b07287425">

                                                                                                                                                                    -VSD-IAT

*   then the titanium is removed by RCA cleaning

*   RCA cleaning --- A solution with

                    De-ionized water(H2O),5parts

                    Ammonium hydroxide(NH4OH),1part

                    Hydrogen Peroxide(H2O2),1part

*  in the last, the local interconnects are :-

  <img width="387" alt="m4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ca669211-e472-41dd-9b78-b4f1a81f9acb">

                                                                                                                                                                   -VSD-IAT

* High Level metal formation

* First we have to put a thick SiO2 layer

  <img width="485" alt="m5" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6e7a3bef-940b-4998-af54-c9752417f477">

                                                                                                                                                                   -VSD-IAT

*  polish this

  <img width="494" alt="m6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ab198fdb-7b3e-40b7-9068-3a3680203eaa">

                                                                                                                                                                   -VSD-IAT

* For contact rules again we have to do a small process

  <img width="386" alt="m7" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d7337afd-f74d-4099-a9ef-8c56467136cc">

                                                                                                                                                                   -VSD-IAT

*  then remove the photo resist

  <img width="389" alt="m8" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/60fdcdb9-81f6-45cf-bb9f-8d9aae87d583">

                                                                                                                                                                    -VSD-IAT

*  then put a titanium metal

  <img width="441" alt="m9" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/99fa22fc-f457-4515-94db-765eec46ff3e">

                                                                                                                                                                    -VSD-IAT

*  then deposit a blanket tungston

  <img width="494" alt="m10" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/56a427f0-49ab-46c7-9a43-78125659d767">

                                                                                                                                                                    -VSD-IAT

*  now again polish it

  <img width="396" alt="m11" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/80db741a-54d3-44a1-be5b-d297e5ce8b27">

                                                                                                                                                                    -VSD-IAT

* now deposit a Aluminium metal

  <img width="495" alt="m12" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6f5a054f-c5c6-4fd1-8ce4-3de2940155b3">

                                                                                                                                                                    -VSD-IAT

*  then use mask13

  <img width="431" alt="m13" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/dec5cd23-c7f7-4e19-a866-b3254a88e9b9">

                                                                                                                                                                    -VSD-IAT

* do plasma etching

  <img width="431" alt="m14" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/dc07a0a9-cbcb-4fd0-a797-65fd100cd6e4">

                                                                                                                                                                    -VSD-IAT

*  then again put SiO2

  <img width="482" alt="m15" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9ca11273-129f-40a4-afa6-e6a186b97714">

                                                                                                                                                                    -VSD-IAT

*  use Mask14 to define holes

  <img width="490" alt="m16" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/47a320fb-2c7e-4455-801d-219d46d67b7f">

                                                                                                                                                                    -VSD-IAT

*  deposit Tin

  <img width="491" alt="m17" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c46ffe58-3a6a-49ec-a694-f8b2a8889e8f">

                                                                                                                                                                    -VSD-IAT

*  deposit W

  <img width="478" alt="m18" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/54f352ea-e630-4832-8ff0-b7c407dc6d02">

                                                                                                                                                                    -VSD-IAT

*  use Mask 15 to define the pattern

  <img width="452" alt="m19" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/0e81b75e-5716-422c-ba44-055c2b17acb7">

                                                                                                                                                                    -VSD-IAT

*  then deposit a layer of Si3N4

  <img width="400" alt="m20" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/04976393-8e53-45fb-9757-467386fd6c3d">

                                                                                                                                                                    -VSD-IAT

*  Use Mask 16 to open contact holes

  <img width="381" alt="m21" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/8e9ebd1d-8b26-4142-a439-28d3967a8506">

                                                                                                                                                                    -VSD-IAT

*  Fabricate/end of Mask-16

  <img width="387" alt="m22" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c6ca3f44-d770-45f3-910c-d04317b81017">

                                                                                                                                                                    -VSD-IAT

## Open source EDA tool development
* Lab exercise : Magic DRC

*  indepth overview of Magic's DRC engine

*  Introduction to google/sky water DRC rules

*  Lab: Warmup experience: Fix a simple rule error

*  Lab: Main exercise: fix or create a complex magic tech

*  to find these all we can search for websites- like open circuit and etc.
 

                                                                                                                                                                   

 

                                                                                                                                                                    

  <img width="191" alt="vv4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2ce547c3-0e88-4214-9e47-9f110109be91">
  ## Labs pictures

  <img width="128" alt="vv" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ebb29f88-336a-490f-aa5c-cc8aede71ec5">

  <img width="452" alt="vv3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a86a1716-2c70-40c6-9bd8-3fbd2904a9c0">                                                                                                                                                                  


 <img width="227" alt="vv2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/91649a47-2e74-4fad-8298-d7eacfd9e6ea">
                                                                                                                                                                    

