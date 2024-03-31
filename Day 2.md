## Day 2

## Define width and hiegh of the core and die
* Lets begin with a netlist
  
  2 FF {Lounch and capture}
  
  1 simple combinational loic inbetween
  
* Netlist picture:- 

  ![Screenshot 2024-03-27 073410](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a5efa844-e004-4eb9-97b8-4a6a8272c9b8)

                                                                                                                                                                     -VSD-IAT

* Means by the picture
  
  FF = Floop/Latches/Registers

  AI,OI = Standerd celld {And,OR,Not,etc}

  Consider a netlist shown connections with above shown connection
  
  Note : A 'netlist' describs the connectivity of an electronic design

* Converting into dimention

  While defining the dimentions we are mostly dependent on the logic gates,also dimentions of OR and AND gate

  Lets give the gates a perfect length and convert it into a physical dimension
                       
  converted netlist look like :-
  
  
  ![Screenshot 2024-03-27 232637](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/135a7903-2912-4118-a02d-16065aab5aa9)

                                                                                                                                                                    -VSD-IAT

  * Final calculation
 
    Lets give a perfect/perticular length,width for both

    It would look like this:-

      ![Screenshot 2024-03-27 080439](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/05667121-0dce-4597-a168-f6e421d11502)

                                                                                                                                                                    -VSD-IAT


    Then we have to bring them together to calculate there area.

    It would look like this:-

    ![Screenshot 2024-03-27 133021](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bd8c407a-041e-4fee-8a2f-044922b88ad1)

                                                                                                                                                                    -VSD-IAT

    now its area will be 4 square units

* first waht is 'core' and 'die' ?
  
  In the section of die we can find the core where the logic gates are present. die is a semiconductor material where the circuits are present. The circuit will not exceed the die.
  
* How to arrive on its dimensions ?
  
  place the logic gates in core

  it ocupies full area

  we have utilized it,it has covered 100% of core so it called as 100% utilization

  Utilization factor = {Area occupied ny netlist}
  
                        ------------------------
  
                        {total area of the core}
  
  Area of netlist :-

  ![Screenshot 2024-03-27 133021](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c1b3b91a-396f-45e3-8848-6f1a5a1cfed9)

                                                                                                                                                                   -VSD-IAT
  
Area of the core :-

![Screenshot 2024-03-27 134914](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/89ac1824-79d4-4c92-bb06-3a7e37aa982c)

                                                                                                                                                                    -VSD-IAT

now utilizatio factor = 4x1/2/2                                                                            
                      =4/4sq
                      =1

The utilization Factor is 1.it means it is fully ytilized{100%}

Aspect Ratio = Height / witdh
             =2/2 unit
             =1

Aspect ratio is 1 

if aspect ratio is 1 then it means it is sqare and if it is any other number is it rectangle 


### calculating by an eg - 1
* If we have 2H and 4W logic factor and 2H and 4W core
* like this :-
  
  ![Screenshot 2024-03-27 133021](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e66617df-8feb-4cb3-bf4b-3b7df3944ede)

                                                                                                                                                                    -VSD-IAT                  

<img width="508" alt="Screenshot 2024-03-27 134338" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ddef44de-0153-4c4f-9c8f-351cada71c28">

                                                                                                                                                                   -VSD-IAT   

utilization factor =0.5 

aspect ratio =0.5


### Calculating by an eg -2 
* If we have 2H and 2W logic factor {same} and 4H and 4W core
* it will look like this :-

  ![Screenshot 2024-03-27 133021](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ff683fca-ad74-4c5e-80ca-b23864f1e50b)

                                                                                                                                                                    -VSD-IAT            

![Screenshot 2024-03-27 134914](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/55652b08-23c0-474b-8e7d-c6e07dfc1069)

                                                                                                                                                                    -VSD-IAT 
                                                                                                                                                                   
 utilization factor = 0.25
 
 aspect ratio = 1


 ## Define locations of preplaced cells
 * What is preplaced cells
 
   Whenever we want to take a part of gates/circuit away from a big circuit and place it in a different circuit the part of circuit taken out is known as pre placed cells.

* actually this work like this

  think this is a circuit and its one part should be implemented.

  ![Screenshot 2024-03-27 140229](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/61257538-5f53-4f7c-80d0-620ce4a67a7e)

                                                                                                                                                                   -VSD-IAT 
    
 cut into half:-

 ![Screenshot 2024-03-27 140424](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68be39c8-15b9-4560-8e32-65b103940088)
 
                                                                                                                                                                  -VSD-IAT                                                                                                                                                                   
 separate it 


 Extand I/O pins 

 ![Screenshot 2024-03-27 140452](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/da511d77-5507-48ce-992d-ad2a3f2333ce)
                                                                                                                                                          
                                                                                                                                                                  -VSD-IAT                                                                                                                                                                                                                                                                                                                
Exttend I/O pins


-![Screenshot 2024-03-27 140643](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e2b2f7b3-4330-4f6a-b580-4a12fba0a505)

                                                                                                                                                                  -VSD-IAT                       

make it black box

![Screenshot 2024-03-27 140609](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/64ed230d-b0b5-4013-9feb-505155213dad)
                                                                            
                                                                                                                                                                    -VSD-IAT

seperate and use                                                                                                                                                                     

![Screenshot 2024-03-27 140643](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/707002d8-04a8-4256-9394-79ca34333cc1)

                                                                                                                                                                    -VSD-IAT

### Its uses and information
* They can be used seperately ,anyware
* Similarly , there are other IP's available

  ![Screenshot 2024-03-27 140920](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bd3483e0-fafc-48c0-b459-1c241f0e7c59)

                                                                                                                                                                    -VSD-IAT

* These are pre placed cells because they are placed only once
* The arrangment of these chip is called floor planning
* these IP's have user-defined locations and hence are placed before automated placement and routing are called pre placed cells
* Automated placement and routing tools places the remaining logical cells in the design on to chip


## Locations of pre placed cells 
### Siding 
* chip will be having two side I/O
* If we get to know the cells should be connected by VCC/VDD.Its placed at 1 side
* Like this

  ![Screenshot 2024-03-27 142149](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7d1e2e61-6dbd-4f8b-9e05-bd5df618971a)

                                                                                                                                                                   -VSD-IAT

### Decapers 
* Some times if the circuits are for the resistance it could be high
* This picture shows the danger of high resistance:-

  ![Screenshot 2024-03-27 143136](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6a0e0288-878e-4154-8b2f-9aaeb2b80773)

                                                                                                                                                                   -VSD-IAT
                                                                                                                                               
* to reduce the resistance we use Decapers
* the decapers are also present in power planning
* like this :-

  ![Screenshot 2024-03-27 143449](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2f361fd5-f106-4633-8342-cd364a0bbd4d)

                                                                                                                                                                    -VSD-IAT

### Charging
* Every cell in the chip will ask the same amount of current supply at some time or their will be a ground bumb.So have many VCC/VDD and GND that will be vary near the cells
* like this :-

  ![Screenshot 2024-03-27 155044](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/947b8059-7842-406a-9d6f-b13abc68327e)

                                                                                                                                                                    -VSD-IAT

 ### Implementation
 * we have 2 sets of circuit of some. It haas FF1,FF21,2{gates},input1,clock1,output1
 * it will look like this :-

   <img width="410" alt="Screenshot 2024-03-27 153222" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c4f8b6e8-65a1-4f85-b06a-740e1d4a5fa3">

                                                                                                                                                                   -VSD-IAT

* another pair of same circuit it has FF1,FF2,1,2{gates} CLOCK1,CLOCK2,OUTPUT,INPUT
* it will look like this

  <img width="409" alt="Screenshot 2024-03-27 153314" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1a887cff-bc5f-4242-b121-ab4d653c8167">

                                                                                                                                                                   -VSD-IAT 

* Then inplement it in the die
* it wil look like this

  <img width="422" alt="Screenshot 2024-03-27 154519" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3533dd39-bdfc-474d-8235-e9ec6737cbbf">

                                                                                                                                                                   -VSD-IAT 

### No placement automatically 
* to prevent auttomatic placement we put a layer around the die
* looks like this.

  ![Screenshot 2024-03-27 155044](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ad3e3187-212b-43d4-879e-c538ad4b1992)

                                                                                                                                                                    -VSD-IAT

## Placement & routing
* Bind netlist with physical cells
  
  The all gates are in sqare shape only
  
  where we can find all cells near that is the library

  ![Screenshot 2024-03-27 165133](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ebed39fd-1999-401b-a7d7-f44d6402f744)

                                                                                                                                                                    -VSD-IAT

  There are 2 types of library
  
  1-consist of all shapes and size
  
  2-it consist information

  it has many sizes

 ![Screenshot 2024-03-29 111849](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/14675585-e4ab-4803-9bdb-f168f5a4b28b)

                                                                                                                                                                  -VSD-IAT 

  as big the size that much less resistance


### Placement 
* placing all three together:

  <img width="602" alt="imp 1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f9075784-9c83-460b-8839-d931fe950b14">

                                                                                                                                                                    -VSD-IAT

* placing netlist in floor plan
* This is the stage where we have time's wire lengh and dcapacitance and based on that,insert repeaters
* like thiss:

   ![Screenshot 2024-03-27 175259](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/84ba0444-2dc8-4274-9e8a-bf7d72141011)

                                                                                                                                                                   -VSD-IAT 

## library characteration and modelling
* veeting the synthesis into ligel hardware is called logic synthesis and the RTL
* we import the logic synthesis output in and dicide the L/W of core and die which is dependent on the gate
* the floor plannning's things are passed to placement where the timing is taken care of
* then to CTS where the 'clock reaches all signals at same time 'is taken care
* Routing is basicaly deparing
* STA where the Arrival and etc are calculated 


## Cell design flow
* It is divided in three points
* Input,Design steps ,outputs
* input - proces design kits {PDKs}:DRC & LVS rules,SPICE models,library & users-defined spes
  
          DRC & LVC = rules in tech file
  
          SPICE = VTO,Y,Kn1,lamda
  
          Library & user -defined spes = cell height,supply voltage,metal layer ,pin location ,drown gate length

* Design steps = circuit design,layout design,charactization
* circuit design = PMOS,NMOS
  
  layout design = graphing a diagram by collours
  
* out puts = CDL,GDSIL,LEF,extracted spice netlist

  <img width="209" alt="imp2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/11ff4d5a-112d-4c71-b062-a061730439d8">

                                                                                                                                                                    -VSD-IAT

## Characterization
* read in the models
* read extracted files
* see the behavior of buffer
* read the sub of inverter
* attach power sources
* apply timeless
* provide output capacitence
* read tran simulation

  1 to 8 is called GUNA
  this will generate timing,noise,pawer,libs,function
  it is divided in three parts :-
   t1ming charactization
   power charactization
   noise charactization

## Timing charactization
* timing threehold definitions

  <img width="233" alt="mp 4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7cf1e8cc-e3f5-4459-a74b-5239c0973f14">

                                                                                                                                                                    -VSD-IAT

* calculation

  <img width="444" alt="p1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bc49cda9-1acc-42b1-be0b-a798637b0c1c">

                                                                                                                                                                    -VSD-IAT

<img width="446" alt="p2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/b58fcfd9-8b9f-454c-9d81-313ae03f06a1">

                                                                                                                                                                    -VSD-IAT

<img width="463" alt="p3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/729573a4-a16a-4261-bf60-375c69e55cd0">

                                                                                                                                                                    -VSD-IAT

<img width="442" alt="p4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/55fd137c-d2f1-4185-9333-8d68b37242fb">

                                                                                                                                                                    -VSD-IAT

<img width="425" alt="p5" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9409a984-70d7-451a-bdf3-f8726fe13fdc">

                                                                                                                                                                    -VSD-IAT

<img width="446" alt="p6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/54266327-4964-44ed-94c2-cdb71a6a8854">

                                                                                                                                                                             
                                                                                                                                                                    -VSD-IAT

<img width="464" alt="p7" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2d3faba8-9cbc-4d07-bd68-90d785af375a">

                                                                                                                                                                   -VSD-IAT

<img width="451" alt="p8" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e0267e8c-69b4-4117-8f41-a907b7aa058a">

                                                                                                                                                                    -VSD-IAT

## Propogation delay
* Equation 

<img width="401" alt="e1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3b5f8be5-327b-4447-9984-e5c5ca049626">

                                                                                                                                                                   -VSD-IAT

* If it is 50%

  eg - 1

  <img width="523" alt="s1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/0ccfe961-edfe-4fce-b14c-a72979162e41">

                                                                                                                                                                   -VSD-IAT 

eg - 2

<img width="535" alt="s2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2b4503ff-7cb0-47e3-9dc7-0880ecff3be2">

                                                                                                                                                                    -VSD-IAT

## Timing characterzation
* Transition time

  Equation

  <img width="425" alt="e2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bbed33ea-97b6-407a-942c-1cad06789bad">
 
                                                                                                                                                                   -VSD-IAT

 it is 20% and others 80% 
![Screenshot 2024-03-27 181027](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/756fac84-9b2e-4eeb-973a-cfd54655589a)


<img width="311" alt="Screenshot 2024-03-26 102123" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ba2f3024-c01b-4cd2-bf45-6fc9d55f43c2">



<img width="504" alt="Screenshot 2024-03-26 151720" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fb2c8bdc-c1c3-4801-b65e-81610dc98b28">



<img width="180" alt="Screenshot 2024-03-26 152245" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4237569f-cfb8-4675-8366-9a6350373c54">

![Screenshot 2024-03-27 161615](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9f90d9be-89c1-4154-9ec5-78fc87bde934)


![Screenshot 2024-03-27 161631](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a98531d5-eada-49b0-9430-bddf5761ea92)


![Screenshot 2024-03-27 161732](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/02509500-217f-4765-8745-9e9212d5e10f)
## pictures while doing labs :-

<img width="209" alt="ll" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/0a12d648-fd83-4b0e-80ea-a227fe5bf469">

![Screenshot 2024-03-27 181027](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/756fac84-9b2e-4eeb-973a-cfd54655589a)

                                                                                                                                                                  -All by me

