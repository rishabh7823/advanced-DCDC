# advanced-DCDC
## Day 1 
## processor/chip 
<img width="406" alt="Screenshot 2024-03-23 121603" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/939d9f5e-9961-4974-8d35-13003d2ce4b7">
“<img width="139" alt="Screenshot 2024-03-23 130930" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7fe8b449-5225-49c2-9f75-27b6a92284fe">

                                                                                                                                                                    -VSD-IAT 


1-This is how the processor looks like


<img width="434" alt="Screenshot 2024-03-23 133754" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fa7375cb-275e-4b8d-b9c8-5c657fe1a509">

                                                                                                                                                                     -VSD-IAT


2-this is the board diagram of the proseccor
 
### The details of the parts and the functioning of parts  

#### **connection of chip**

The chip is present at the middle and to connect the chip we  use something called as wire pounds.wire pounds help chip to connect with other parts. 


#### **important things inside the chip**

1-*PADS* 

PADS is somthing from which you can send the signals inside the chip 

2-*CORE* 

CORE is something where all our digital logic are placed 

3-*DIE* 

DIE is the size of the chip which is manufactured on the silicon 


#### **Woking inside the chip**

1.The tipical chip/core consist of RISCV SoC,SRAM,PILL,adc,adc1,dac,SPI

2.The SRAM ,PILL,adc,adc1,dac are called as foundry IP's

3.The RISCV SoV and SPI are called Macros 


#### **Foundry IP's**

1.example of Foundry IP's is Rath 150

2.Foundry is basically a set of machines/a big factery and we communicate with the factery as a VLSI engineer.

3.IP is bassically called intelligent property it means it needs some extra intelligens to build this.


#### **Macros**

1.Macros are digital logic and needs IP's 

### RISC-V Instruction Set Architecture {ISA}
* If we want to transfer a C code to a computer/hardwar.Its first made to a assembly language program/RISC-V assembly language and to machine language program/binary program language then its passed to the layot.
* we have to implement RISC-V specification to some RTC and then to the layot.

#### lets go more deep 
* The apps enter our computer in this way :-
APPS -> System Software -> Hardware/chip
* types/parts of apps,system software,hardware
**app**-firefox,google and etc
**system software**-OS,Compiler,Assembler
  **hardware**-INTEL,Apple and etc

#### Work of OS

  **Major work**-
  * Converts the app into the assembly program
    
    **Miner work** -
    * low level system function
    * handle IO operations
    * Alocate memory

#### Compiler 
* converts the languages into instructions.
* the instructios will be in chips format.

#### Assembler 
* It converts the instructions into the binary language.

#### Abstract interface 
* The instruction s act act like the abstract interface between the language and the hardware.
* its also called as Instruction Set Architecture or Architecture of computer

#### Understanding of hardware
* The binary is sent to a RTL which will convert the binary into gate level undertanding
* It is passed to the hardware and then gets done by the chip

### SoC Design Using Openlane
**Lets start with ASIC**

digital ASIC diagram:-

<img width="336" alt="Screenshot 2024-03-24 122708" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/015eaaa9-db57-49ba-9ed8-d07805bfdded">

                                                                                                                                                        -VSD-IAT

The properties needed for ASIC :-

<img width="514" alt="Screenshot 2024-03-24 123120" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/24c8460e-7e8d-467c-be2b-c0f3f243744b">

                                                                                                                                                          -VSD-IAT

#### **open sources**  
* RTL Design = Librecares.org
               Opencores.org
               Github.com
* EDA Tools = Qflow
              OpenRoad
              OpenLone
              {The cathods}

#### What is a PDK?
* PDK = the interface between the FAB and the design
* PDK = Processer Designing Kit

#### How it works 
* Collection of files used to madel the EDA
* Process design rules:DRC,LVS,PEX
* Device models
* Digital stantard cell libraries
* I/O libaries

#### Formation of PDK
* Google singed a agreement with skywater to make a PDK of 13nm and it was lounched at june 30 2020 and was the first ever open source PDK.

#### is 130nm old ?
*you could get the answer by this pie chart*

<img width="438" alt="Screenshot 2024-03-24 125836" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e4f99bfd-4432-433c-b490-b306a950f578">

                                                                                                                                                                     -VSD-IAT

#### Is 130nm fast?
* Intel:P4EE @ 3.46GHz{Q4'O4}
* OSU team reparted 327 MHz post-layot clock frequency for a single cycle RV32:CPU
* Apipelined version xan achieve > 1GHz clock

#### ASIC Design Flow 
* ASIC Flow objective:RTL to GDSIL
* Also called Automated PnR  and Physical Implementation

### RTL to GDSIL Flow 
<img width="602" alt="Screenshot 2024-03-24 131046" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c2ce7a94-a1d7-4caf-8dbe-9c973a26b19a">

                                                                                                                                                                    -VSD-IAT
#### Synth 
* Converts RTL to a circuit out of components from the stanserd cell library {SCL} 
* Basically it converts the RTL into gate levels netes
* 'Standard cells' have regular layouts
* Each has different views
-Electrical,HDL,SPICE
-Layout

#### FP+PP
* It bassically means floring the chip
* Chip floor - planning : partition the chip die between different system building blacks and place the I/O pads
* Macro floor planning : we difine Dimensions,Pin location,raws definition
* Power planning : The chip is pawered by VCC,VDD and they are conected to each other . they us uper metal layers hence have less resistance

#### Place 
* Place the cells on the floor plan rows,aligned with the sites are placed near to each other to low the resistance
* usually done in 2 steps : Global,Detailed
* Glogal teris to find optinal positions for all cells and the cells could overlap
* Detailed are mininally alterd and the cells does not overlap

#### Clock tree synthesis
* create a clock distribution network
* To deliver the clock to all sequention elements
* with minimum skew
* and in a good shape
* usually a tree

#### Routing
* Implement the intarconnect using the available metal layer
* The first one is made by titium and other are aluminium
* metal tracks form a routing grid
* Routing grid is huge
* Divid and conque
* Global Routing : Generates routing guides
* Detailed Routing : Uses the routing guides to implement the actual wiring

#### Sign off 
* Physical varifications

  Design Rules Checing{DRS}
  
  Layout vs Schematic {LVS}
  
* Timing Verification

  static timing analysis {STA}


### OpenLane
* Started as an open source flow for a true open source tape-out Experiment
* Strive is a family that opens everything in SoCS

  Opens PDK ,open ED,open RTL 
* It has several families and benefits like :-
  sTriVe:SKy 130SCL+Synthesized 1Kbytes SRAM
  sTriVe2:SKy 130SCL+1Kbytes open RAM block
  sTriVe2a:sTriVe 2 with a single chip core module
  sTriVe 3: OSU SCL+Synthesized 1Kbytes SRAM
  sTriVe5SKY130SCL+8x1Kbytes open RAM banks
  sTriVe6:sTriVe2 with DFT

### OpenLane ASIC flow 
* Maain Goul: Produce a clean GDSIL with no human interaction
  clean : No LVS violation
  
  
          No DRC violation
  
  
          No Timing violation {in progeres}
  
  
* for example : SKy 130nm openPDK functions :-
  
  Functional out at the box
  
  Instructions tobuild and run natively will follow

* Can be used to harden Macros and chips

  harden to generate final layout

* Two modes of operation
  
  Autonomous:figure out the flow
  
  Interactive:xan operate commands and steps one on one

* Design space exploration
  Find the best set of flow configuration
  used to find sets block of figurations
  
  large number of design example
  
  43 design with their best configuration

### actual openlane ASIC flow

 <img width="590" alt="Screenshot 2024-03-26 090801" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/0fea7ae3-2e5c-4fe9-86df-4932b1525d6a">

                                                                                                                                                                    -VSD-IAT
Openlane is based on several open sorsues 

open soursues like : OpenROAD,Yosys,ABC,Fault 

<img width="94" alt="Screenshot 2024-03-26 091409" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ac2d334c-883e-4c64-8f3f-a9769598c8b5">
                                                                                                                                                                     
                                                                                                                        -VSD-IAT
lets get started with this 👆

* 1 - first it goes tthrew RTL Synthesis where the yoys converts it into circuits and ABC needs coupration while optimitation
* 2 - STA it means Synthesis Startegy it targut the least area and perfect timing.Used to achive objects
* 3 - Synthesis exploration is used to create a report that show the delay and area from this we can pic the best strategy to continue
* 4 - Design Exploration also generates a report that shows different design mattries and no of violation generated after generating the final layout
  
  The design exploration utility is also used for regression testing{CI}
  
  We run openlane on-70 design and compare the results to the best known ones
  
* 5 - Design for test {DFT}. if we want to do testing after fabrication we can enable DFT.This is optional
  
  Scan Insertion
  
  Actomatic test pattern Generation{ATPG}
  
  Faut coverge
  
  Fault Simulation
  
  This processs is done by Fault
  
  like this :-

  <img width="348" alt="Screenshot 2024-03-26 094723" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9758d111-f184-4534-9f1f-8e6b8f556677">

                                                                                                                                                                     -VSD-IAT

* 6 - Physical Implementation

  Also called outomated PnR {Place and Route}

  Floor/Power Planning

  End decoupling capacitors and tap cells insections

  Placement:Global and Detailed

  Past placement optimitation

  Clock Tree Synthesis {CTS}

  Routing :Global and Detailed

  This process is done by openROAD


* 7 - Logic Equivalence Ckeck {LEC}
  
  the netlists modified,verification must be performed

  CTS modifies the netlist

  Past placement optimization modification the netlist

  LEC is used to formally confirm that the function did not change after modifying the netlist

  This process is done bt yosys

* 8 - Dealing with Antenna Rules violations
 
  when a metal wire segment is fabricated it can act as an antenna

  reactive ion etchin causes chare to accumalate on the wire

  transister gates can be damagged during fabrication

  this is done in 2 steps :-
  1-Bridging attaches a higher layer intermadiary
  
   -require router awarness
  
    -like this

  <img width="345" alt="Screenshot 2024-03-26 101127" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/30deb001-1732-4c6b-b82b-736acf245467">

                                                                                                                                                                    -VSD-IAT


 2- Add antenna diode cell to leak away charges
 
    Antenna diodes are provided by the SCI
    
    like this

  

  <img width="121" alt="Screenshot 2024-03-26 101328" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9eb8c578-b905-4610-90f6-99ad571f8da1">

                                                                                                                                                                    -VSD-IAT

  We can take a few preventive approach

  1 - Add a false antenna Diode next to every cell input after placement
  
  2 - Run the antenna checker {Magic} on the routed layout
  
  3 - If the checker reportsa violation on the cell input pin,replace the fake diode cell by a real once

  4 - like this :-

  <img width="233" alt="Screenshot 2024-03-26 101752" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/357884cd-5990-48d4-930d-cac070385593">

                                                                                                                                                                    -VSD-IAT

* 9 - Static timing Analysis
* 
  RC Extraction :DEF2SPEF
  
  STA: open STA {openROAD}

  like this :-

  <img width="311" alt="Screenshot 2024-03-26 102123" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2b1af3d8-1128-4b41-9197-1c96dffc82ee">

                                                                                                                                                                     -VSD-IAT

* 10 - Physical Verification DRC&LVS

  Maigic is used for Design Rules checking and SPICE Extraction from layout

  Magic and Netgen are used for LVS

  Extracted SPICE by Magic vs verilog netlist


  ### All the codes of openlane
  * cd = a universal code/helps u in many things
  * ls -ltr = helps to search many things
  * clear = clears every thing
  * help = it shows many codes
  * mkdir = to create a file
  * cd ../ = undo
  * etc/many more

  ### pictures while doing the labs


<img width="287" alt="Screenshot 2024-03-26 130232" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/08ce3914-ebf1-434f-bb45-d8212801d2c8">



<img width="180" alt="Screenshot 2024-03-26 152245" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/28e8d8a4-458d-4cee-aa4a-a003c690a80f">





<img width="287" alt="Screenshot 2024-03-26 151732" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c75e7b8d-0864-484e-a545-5a86ad051f0b">


  

<img width="950" alt="Screenshot 2024-03-26 151959" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d433d415-5bdb-4aab-ad35-782c29037f0d">

                                                                                                                                                                   -all by me


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

  Lets give the gates a perfect lenth and convert it into a physical dimensical

  converted netlist look like :-
  
  
  ![Screenshot 2024-03-27 232637](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/135a7903-2912-4118-a02d-16065aab5aa9)

                                                                                                                                                                     -VSD-IAT


  * Final calculation
 
    Lets give a perfect/perticular lenth,width for both

    It would look like this:-

      ![Screenshot 2024-03-27 080439](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/05667121-0dce-4597-a168-f6e421d11502)

                                                                                                                                                                    -VSD-IAT


    Then we have to bring them together to calculate there area.

    It would look like this:-

    ![Screenshot 2024-03-27 133021](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bd8c407a-041e-4fee-8a2f-044922b88ad1)

                                                                                                                                                                    -VSD-IAT

    now its area will be 4 square units

* first waht is 'core' and 'die' ?
  
  In the section of die we can find the core. core where the logic gates are present. die is a semiconductor metirial where the circuits are present. The circuit will not exid the die.
  
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
 
   Whenever we want to take a part os gates/circuit away from a bigb circuit and place it in a different circuit the part of circuit taken out is known as pre placed cells.

* actually this work like this

  think this is a circuit and its one part should be implemented.

  ![Screenshot 2024-03-27 140229](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/61257538-5f53-4f7c-80d0-620ce4a67a7e)

                                                                                                                                                                    -VSD-IAT 
    
 cut into half:-

 ![Screenshot 2024-03-27 140424](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68be39c8-15b9-4560-8e32-65b103940088)
 
                                                                                                                                                                    -VSD-IAT                                                                                                                                                                   
 seprate it 


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

* These are pre placed cells because they are placed only ones
* The arrangment of these chip is called floor planning
* these IP's have user-defined locations and hence are placed before automated placement and routing are called pre placed cells
* Automated placement and routing tools places the remaining logical cells in the design onto chip


## Locations of pre placed cells 
### Siding 
* chip will be having to side I/O
* If we got to know the cells should be connected by VCC/VDD.Its placed at 1 side
* Like this

  ![Screenshot 2024-03-27 142149](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7d1e2e61-6dbd-4f8b-9e05-bd5df618971a)

                                                                                                                                                                     -VSD-IAT

### Decapers 
* Some times if the circuits are for the resistance could be high
* This picture shows the danger of high resistance:-

  ![Screenshot 2024-03-27 143136](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6a0e0288-878e-4154-8b2f-9aaeb2b80773)

                                                                                                                                                                     -VSD-IAT
                                                                                                                                               
* to reduse the resistance we use Decapers
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

* another of same circuit it has FF1,FF2,1,2{gates} CLOCK1,CLOCK2,OUTPUT,INPUT
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

## Plcement & routing
* Bind netlist with physical cells
  
  The all gates are in sqare shape only
  
  where we can find all cells near thats the is liberary

  ![Screenshot 2024-03-27 165133](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ebed39fd-1999-401b-a7d7-f44d6402f744)

                                                                                                                                                                    -VSD-IAT

  There are 2 types of library
  
  1-consist of all shapes and size
  
  2-it consist information

  it has many sizes

 ![Screenshot 2024-03-29 111849](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/14675585-e4ab-4803-9bdb-f168f5a4b28b)

                                                                                                                                                                    VSD-IAT 

  as big size that less resistance


## Plcement 
* placing all three together:

  <img width="602" alt="imp 1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f9075784-9c83-460b-8839-d931fe950b14">

                                                                                                                                                                    -VSD-IAT

* placing netist in floor plan
* This is the stage where we as time's wire lengh and dcapacitance and based on that , insert repeaters
* like thiss:

   ![Screenshot 2024-03-27 175259](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/84ba0444-2dc8-4274-9e8a-bf7d72141011)

                                                                                                                                                                    -VSD-IAT 

## library characteration and modelling
* can veeting the synthesis into ligel hardware is called logic synthesis and the RTL
* we import the logic synthesis output in and dicide the L/W of core and die which dependent on the gate
* the floor plannning's things are passed to placement where the timing is taked care of
* then to CTS where the 'clock reches all signals at same time 'is taken care
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
* see the behavior of beffer
* read the sub of inverter
* atach pawer sorces
* apley stimless
* provide output capasitence
* read tran simulation

  1 to 8 is called GUNA
  this will generate timing,noise,pawer,libs,function
  it is divided in three parts :-
   t1ming charactization
   pawer charactization
   noise charactization

## Timing charactization
* timing threehold definitions

  <img width="233" alt="mp 4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7cf1e8cc-e3f5-4459-a74b-5239c0973f14">

                                                                                                                                                                    -VSD-IAT

* clculation

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

  Eqation

  <img width="425" alt="e2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bbed33ea-97b6-407a-942c-1cad06789bad">
 
                                                                                                                                                                   -VSD-IAT

If its 20% and others 80% 

## pictures while doing labs :-

![Screenshot 2024-03-27 181027](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/756fac84-9b2e-4eeb-973a-cfd54655589a)


<img width="311" alt="Screenshot 2024-03-26 102123" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ba2f3024-c01b-4cd2-bf45-6fc9d55f43c2">



<img width="504" alt="Screenshot 2024-03-26 151720" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fb2c8bdc-c1c3-4801-b65e-81610dc98b28">



<img width="180" alt="Screenshot 2024-03-26 152245" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4237569f-cfb8-4675-8366-9a6350373c54">

![Screenshot 2024-03-27 161615](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9f90d9be-89c1-4154-9ec5-78fc87bde934)

![Screenshot 2024-03-27 161631](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a98531d5-eada-49b0-9430-bddf5761ea92)

![Screenshot 2024-03-27 161732](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/02509500-217f-4765-8745-9e9212d5e10f)

                                                                                                                                                                  -All by me


## Day 3 
## VTC - SPICE simulation 
* Spice Deck
  
  component connectivity {netlist}

* PMOS :-

  ![Screenshot 2024-03-28 164130](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f41867c6-91d2-4958-947e-f43272acdcbc)



* NMOS :-

  ![Screenshot 2024-03-28 164136](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f0c88b9f-d0bf-4030-a39b-01c6ac133db7)



* Component value

  Like :-

  ![Screenshot 2024-03-28 164450](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/81b3bebb-b7b5-46b2-bd4d-1026268cd5ab)

* Identify nodes

  nodes :- a gate in between two objects.The object is the node.

  ![Screenshot 2024-03-28 164645](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a9c9c4aa-1795-44bb-8097-d90896ae581b)



* name the nodes

  ![Screenshot 2024-03-28 165024](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/48f57bd1-2d6a-489f-9b92-d0233479ec21)



* *** Model Description ***
* *** Netlist Description ***

  M1 out in vdd pmos W=0.375U
  
                     L=0.25U

  M2 out in 00 nmos W=0.375U

                    L=0.25U

  Cloud out 0 10f

  Vdd vdd 02.5

  Vin in 02.5


* Simulation Commands
 
    .op

    .dc vin 02.5  0.05


* *** include tsmc_025um_modes1.mod***
 
    LTB -"tsmc_025um_modes1.mod"

    CMOS_MODEIS.end


* eg - 1 = SPICE waveform : Wn - Wp=0.375u,Ln,p=0.25u device (Wn/Ln=Wp/Lp=1.5)
 
    ![Screenshot 2024-03-28 171031](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9011f0ab-798c-4b12-97a9-56bd1128c992)



* eg - 2 =   SPICE waveform : Wn=0.375,Wp=0.9375u,Ln,p=0.25u device (Wn/Ln=1.5,Wp/Lp=2.5)

  ![Screenshot 2024-03-28 171320](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/14a5abba-a6e9-4c6d-9ffd-8a876024295a)


  
* Difference between eg1 and eg2

   we can see that eg1 is little to left and eg2 is middle

   this show that the CMOS is Robustness
  
   Static behaviour evaluation : CMOS invertor Robustness, Switching threshold,Vm

   Switching threshold is the point switches

   Vm is a point where Vin=Vout

  eg 1 =

  ![Screenshot 2024-03-28 224645](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3fe8cd74-a109-4cc0-addc-71f5a32f1540)


    
 eg 2 = 

 <img width="261" alt="eg 1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c782984f-ac94-439c-b0f1-3872b831c798">



 Vm = 

 <img width="535" alt="all" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4a6e05f8-1562-48f4-b1b5-da1b2a597681">



 Then in eg1 vgs = vds 

 ![Screenshot 2024-03-28 175340](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9731518f-90e8-4133-b914-a8156a2444bd)



 equations:

 Vm=R.Vdd/(1+R)

 R=KbVdsatp/KnVdsatn = (w/p)Kp1.Vdsatp/(Wn/Ln)Kn1.Vdsatp

                   Kn.Vdsatn(Vm-Vt)-Vdsatn/2
(Wp/Lp)/(Wn/Ln) = ________________________________
                   Kbl.Vdsatb(-Vm+Vdd+Vt)+VdsatB/2

eg.1 rise and fall in waveform 

![Screenshot 2024-03-28 172902](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bbba624c-5be7-4c0a-ac9f-cff78f0fb41c)



## 16-mask CMOS process
* selecting a substrate

  will take a normal block

  ![Screenshot 2024-03-28 193231](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68c2ceb3-d415-4fb4-97a2-bf52bd08b0da)



called P-substrate
* Creating a active region for transistors

  Create isolation between all substrate

  Mask1 is the layout

  with layers

  ![Screenshot 2024-03-28 194206](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ef292f21-1ecc-4f5c-8873-42d27fe6e2c0)

  

 poto washed away

 <img width="494" alt="e" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/be97bdb1-c7ad-45bd-af75-429f25aa8145">



 chemically removed

 ![Screenshot 2024-03-28 194810](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/888e6b08-4681-46c4-928e-b6014ed6260d)



 Bird's breack

 <img width="593" alt="r" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d7626e44-074b-4e61-8cf2-63f8f85b1ea4">



* N-well and P-well formation

  Mask look like

  <img width="600" alt="l" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6b087dc3-d57d-492a-b455-67fa69d781e7">



  Layers

  ![Screenshot 2024-03-28 195258](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/da375175-bb75-4cee-a1cb-42603e97df4c)



  then implement P-MOS like this

  ![Screenshot 2024-03-28 195538](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/208789ea-1232-4495-9c92-10bfb673d840)



  then implement N-MOS like this

  ![Screenshot 2024-03-28 195731](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/178694c4-ac82-4d30-8421-c3f3845546b9)



  In the last we can see this

  ![Screenshot 2024-03-28 200626](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9e07e02d-9aa9-4234-9d29-3bda8ef999f9)



  to expand P,N MOSS we put it in high temperature

  <img width="475" alt="k" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/248e764e-727a-4b76-a37a-4bd8b004f5cc">



* Formation of "gate"

  for creating douping concentration in PMOS

  ![Screenshot 2024-03-28 200626](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/de76fc05-731f-4902-8c70-1eadc2e4556a)



  for creating douping concentration in NMOS

  ![Screenshot 2024-03-28 200838](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/bc095e15-e7da-4210-9f38-84e0d289a690)



  As the oxide is damaged originally, so the oxide is etched usin dilute hydroflouric acid{HF}

![Screenshot 2024-03-28 202240](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/68ecab63-006d-4f79-a58d-d1598db56fee)



Then regrow it again {10n thin}to put in the gates,first we put many layers

<img width="431" alt="h" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1f296214-b6c9-4859-b956-f45d77bf448e">



by UV light the layers are eched away

![Screenshot 2024-03-28 203325](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/5b33ace0-4874-4565-9da1-4a00830130e8)



In the last this is the gate we get

![Screenshot 2024-03-28 203401](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/536d63f7-68f5-4c60-8d56-f38fa6a43f60)



* Lihtly Doped Drain{LDD} formation

  while fabricating in NMOS in P-well, we get source and drain and they both are P type, which is P+

  P-  is the LDD

  N is N well

  So we have 3types of doping for NMOS - P+, P-, N

  Here source and drain are N

  N- is LDD

  P is P-well

  So we have 3 types of doping for PMOS - N+,N-, P

  * Why we need these all

    there are 2 reasons for this

    Hot electron effect

    Short channel effect

  * Hot Electronic effect
 
    electronic fold  E=V/d

    High Energy carriers break si-si bonds

    3.2.v barrier between Si conduction band

    SiO2 conduction band

* Short channel effe
  For short channel, drain field penetrates as channel

* process for implant

  ![Screenshot 2024-03-28 210634](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d8451a4c-0de5-4895-90ca-8e42d58f907e)


  👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇👇

  ![image](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1eb940e5-99c8-4e8d-a096-40c1c8b45475)


 
  To protect the implemented N,P we use SiO2. Then Plasma anisotropic etches it. some side wall spaces are created protects.

* Source and drain formatio

  To make N+ in P-wall

  ![Screenshot 2024-03-28 211005](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ca0f34d4-09cb-4e8b-bb04-7588c4b5617d)



  To Make P+ in N-wall
 
  <img width="417" alt="p1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a5b0078f-1619-4381-af16-f2b84589c5d8">



  then in high temperature

![Screenshot 2024-03-28 211615](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/85209953-9143-439d-84c5-8674a226fcfe)

  
