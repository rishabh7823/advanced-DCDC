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

### **connection of chip**

The chip is present at the middle and to connect the chip we  use something called as wire pounds.wire pounds help chip to connect with other parts. 


### **important things inside the chip**

1-*PADS* 

PADS is somthing from which you can send the signals inside the chip 

2-*CORE* 

CORE is something where all our digital logic are placed 

3-*DIE* 

DIE is the size of the chip which is manufactured on the silicon 


### **Woking inside the chip**

1.The tipical chip/core consist of RISCV SoC,SRAM,PILL,adc,adc1,dac,SPI

2.The SRAM ,PILL,adc,adc1,dac are called as foundry IP's

3.The RISCV SoV and SPI are called Macros 


### **Foundry IP's**

1.example of Foundry IP's is Rath 150

2.Foundry is basically a set of machines/a big factery and we communicate with the factery as a VLSI engineer.

3.IP is bassically called intelligent property it means it needs some extra intelligens to build this.


### **Macros**

1.Macros are digital logic and needs IP's 

### RISC-V Instruction Set Architecture {ISA}
* If we want to transfer a C code to a computer/hardwar.Its first made to a assembly language program/RISC-V assembly language and to machine language program/binary program language then its passed to the layot.
* we have to implement RISC-V specification to some RTC and then to the layot.

### lets go more deep 
* The apps enter our computer in this way :-
APPS -> System Software -> Hardware/chip
* types/parts of apps,system software,hardware
**app**-firefox,google and etc
**system software**-OS,Compiler,Assembler
  **hardware**-INTEL,Apple and etc

### Work of OS

  **Major work**-
  * Converts the app into the assembly program
    
    **Miner work** -
    * low level system function
    * handle IO operations
    * Alocate memory

### Compiler 
* converts the languages into instructions.
* the instructios will be in chips format.

### Assembler 
* It converts the instructions into the binary language.

### Abstract interface 
* The instruction s act act like the abstract interface between the language and the hardware.
* its also called as Instruction Set Architecture or Architecture of computer

### Understanding of hardware
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

### **open sources**  
* RTL Design = Librecares.org
               Opencores.org
               Github.com
* EDA Tools = Qflow
              OpenRoad
              OpenLone
              {The cathods}

### What is a PDK?
* PDK = the interface between the FAB and the design
* PDK = Processer Designing Kit

### How it works 
* Collection of files used to madel the EDA
* Process design rules:DRC,LVS,PEX
* Device models
* Digital stantard cell libraries
* I/O libaries

### Formation of PDK
* Google singed a agreement with skywater to make a PDK of 13nm and it was lounched at june 30 2020 and was the first ever open source PDK.

### is 130nm old ?
*you could get the answer by this pie chart*

<img width="438" alt="Screenshot 2024-03-24 125836" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e4f99bfd-4432-433c-b490-b306a950f578">

                                                                                                                                                                     -VSD-IAT

### Is 130nm fast?
* Intel:P4EE @ 3.46GHz{Q4'O4}
* OSU team reparted 327 MHz post-layot clock frequency for a single cycle RV32:CPU
* Apipelined version xan achieve > 1GHz clock

### ASIC Design Flow 
* ASIC Flow objective:RTL to GDSIL
* Also called Automated PnR  and Physical Implementation

### RTL to GDSIL Flow 
<img width="602" alt="Screenshot 2024-03-24 131046" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c2ce7a94-a1d7-4caf-8dbe-9c973a26b19a">

                                                                                                                                                                    -VSD-IAT
### Synth 
* Converts RTL to a circuit out of components from the stanserd cell library {SCL} 
* Basically it converts the RTL into gate levels netes
* 'Standard cells' have regular layouts
* Each has different views
-Electrical,HDL,SPICE
-Layout

### FP+PP
* It bassically means floring the chip
* Chip floor - planning : partition the chip die between different system building blacks and place the I/O pads
* Macro floor planning : we difine Dimensions,Pin location,raws definition
* Power planning : The chip is pawered by VCC,VDD and they are conected to each other . they us uper metal layers hence have less resistance

### Place 
* Place the cells on the floor plan rows,aligned with the sites are placed near to each other to low the resistance
* usually done in 2 steps : Global,Detailed
* Glogal teris to find optinal positions for all cells and the cells could overlap
* Detailed are mininally alterd and the cells does not overlap

### Clock tree synthesis
* create a clock distribution network
* To deliver the clock to all sequention elements
* with minimum skew
* and in a good shape
* usually a tree

### Routing
* Implement the intarconnect using the available metal layer
* The first one is made by titium and other are aluminium
* metal tracks form a routing grid
* Routing grid is huge
* Divid and conque
* Global Routing : Generates routing guides
* Detailed Routing : Uses the routing guides to implement the actual wiring

### Sign off 
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

  ## pictures while doing the labs


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


### Plcement 
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

  ## Labs pictures

  <img width="128" alt="vv" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ebb29f88-336a-490f-aa5c-cc8aede71ec5">

                                                                                                                                                                    -VSD-IAT

  <img width="227" alt="vv2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/91649a47-2e74-4fad-8298-d7eacfd9e6ea">

                                                                                                                                                                    -VSD-IAT

  <img width="452" alt="vv3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a86a1716-2c70-40c6-9bd8-3fbd2904a9c0">

                                                                                                                                                                    -VSD-IAT

  <img width="191" alt="vv4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2ce547c3-0e88-4214-9e47-9f110109be91">

                                                                                                                                                                    -VSD-IAT


## Day 4 
## Power Aware CTS
* The AND gate could be used as supply of clock, like this

  <img width="135" alt="q" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ea395b13-0aff-4b74-9f27-381350138559">

                                                                                                                                                                    -VSD-IAT

*  Also we can use OR gate like this:

  <img width="111" alt="q1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/891d09ee-1f92-46b3-bfbb-0bc846042b19">

                                                                                                                                                                    -VSD-IAT

* How it uses the clock drain

  Lets think we have a circuit like this:

  <img width="317" alt="q2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6e5e35fd-2906-4cdc-b80d-8c5640134211">

                                                                                                                                                                    -VSD-IAT

### Assumsion

*  Let us assume C1=C2=C3=C4=25FF

*  Createa buffer tree at Node 'A'

* Let us assume Cbuf1=Cbuf2=30FF

* total Cap at node"A' - 60FF

*  total cap at node'B' - 50FF

*  total cap at node'C'-50FF

### Observations

*  2 levels of buffering

*  At every level, each node driving same load

*  identical buffer at same level

## but the delay was varying

*  for this the engineers found a table called daly table for CBUF'1'-Size1

*  it looked like this:

  <img width="272" alt="q3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/5291448a-43e0-4861-8992-4b8cab3742a4">

                                                                                                                                                                    -VSD-IAT

### Lets do with a eg (CBOF'1')

*  lets think the input is 60ps

*  lets think the output is 70FF

*  then the delay will be 16x

## Size of Delay tables

*  Delay table size 'CBOF'1''

  <img width="272" alt="q3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/2ce5cb8c-3831-4c78-ac9d-6234773ff2e4">

                                                                                                                                                                    -VSD-IAT

*  Delay table size 2'CBOF'2''

  <img width="263" alt="q4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/b8de881e-d05d-415b-98b0-b06a383b86cb">

                                                                                                                                                                    -VSD-IAT

### Lets do with eg-1

*  assume the input is 40ps 'size1'

*  assume the output is 60FF 'size1'

*  the delay will be x9.5 'size1'

  <img width="222" alt="q5" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9c395938-a1ff-4974-a674-c99e60d65636">

                                                                                                                                                                    -VSD-IAT

*  assume the input is 60ps 'size2'

*  assume the output is 50FF 'size2'

*  the delay will be y15'size2'

  <img width="229" alt="q6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6b9bdadc-92a3-459d-b90c-63f269c7bd7e">

                                                                                                                                                                    -VSD-IAT

 * the last 2 dont have any skew'O'

  <img width="235" alt="q7" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/dd989f48-c265-4868-89ba-01d5ac2c13fd">

                                                                                                                                                                    -VSD-IAT

*  these two are not active

  <img width="278" alt="q8" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d52e06a7-3aa9-4a3b-9cd9-23b49cb9eeb0">

                                                                                                                                                                    -VSD-IAT

## Setup Timing Analysis
### Timing Analysis

*  Specifications

  Clock frequency(F) = 1GHz

  Clock period(I) = 1/F

                  = 1/GHz

                  = 1ns

 * the full circuit:

  <img width="500" alt="q9" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/78afb444-d4cb-49a3-8879-6c9d51645c01">

                                                                                                                                                                    -VSD-IAT

* inside capture Flab

  <img width="794" alt="q10" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e6493235-a76f-4db1-bbec-84737135b81a">

                                                                                                                                                                    -VSD-IAT

*  Hence finite time'S' required for 'D'to reach Qm

*  ⊖<T but now Q<(T-S)

  <img width="509" alt="q11" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4656775b-f9ae-4272-b23d-61034bdf2d47">

                                                                                                                                                                    -VSD-IAT

### litter

*  window within which clock edge can arrive on real chip

*  Temporary variation of clock period

  <img width="541" alt="q12" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/acfa2ded-6498-4ee3-b682-67cf895c507d">

                                                                                                                                                                  -VSD-IAT                                                                                                                                                          

 * now it is in the single box

  <img width="488" alt="q13" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/43900ef1-d717-4ddc-a6a6-9651da2f1f8d">

                                                                                                                                                                  -VSD-IAT                                                                                                                                                                 

*   ⊖<(T-S) but now ⊖<(T-S-Su)

### Now lets find the time delay from our old design

  <img width="284" alt="q14" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1efd2295-25f0-45ba-aaa1-1a79850cccec">

                                                                                                                                                                    -VSD-IAT

*  ⊖ = FF1(CLK-Q)

  + wire delay estimate1

  + delay of '1'

  + wire delay estimate2

  + delay of '2'

  + wire delay estimate3
 
  <img width="170" alt="q15" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e70da565-ef59-4d6a-baa8-15e2d25d9f9e">
  
                                                                                                                                                                    -VSD-IAT

*  ⊖ = FF1(CLK-Q)

  + delay of '1'
 
  + delay of '2'
 
*  delays

  ⊖<1ns-0.01ns-0.09ns

  <0.9ns


### CTC problems

 * Let's put the wire in proper form in our old design

  <img width="421" alt="q16" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1bcb6c11-5f8f-48a8-accc-247c5eb6a600">

                                                                                                                                                                    -VSD-IAT

*  Problem

  the problem in Section1:

  it actually looks like this:

  <img width="490" alt="q17" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/f9b71100-b80a-48b5-ba0d-fef064ccc4c8">

                                                                                                                                                                    -VSD-IAT

*  the time to reach FF1 is t1

*  the time to reach FF2 is t2

  <img width="487" alt="q18" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a876979d-ba96-4579-aa36-f9bce6ba417e">

                                                                                                                                                                    -VSD-IAT

*  t2-t1=skew

*  skew should be ~'ops'

*  the route will not give '~ops' and thats the problem

  <img width="605" alt="q19" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3a9cbe66-136c-4730-a3df-e40726cb6361">

                                                                                                                                                                    -VSD-IAT

 * it should be like this

  <img width="406" alt="q20" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9354c8a7-0817-4857-a39f-defe6c357b18">

                                                                                                                                                                    -VSD-IAT

*  This is a H-Tree

*  in last we add Buffers(Buffering)

  <img width="407" alt="q21" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fff9128d-3892-4c0b-9565-ec74047a1429">

                                                                                                                                                                    -VSD-IAT

*  Then Net shielding which will protect the wiring

  <img width="401" alt="q22" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/48bd5427-9ece-4aa9-a574-6982203877af">

                                                                                                                                                                    -VSD-IAT

*  or else there would be glitch

###  What is glitch

*  When two circuits are near, from one circuit the vibration would pass to another circuit from which memory loss would happen.

  <img width="312" alt="q23" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/67a0bcc3-f9c4-40ca-854c-ab23aa9c4f4e">

                                                                                                                                                                    -VSD-IAT

                                                       👇👇👇


  <img width="305" alt="q24" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1ee067b8-b29a-4763-8800-3fea872c5aad">

                                                                                                                                                                   -VSD-IAT

### Lets now make it with real clock

* now this looks like this

  <img width="483" alt="q25" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fdae677e-dd02-4ac1-ba31-a0060b94515a">

                                                                                                                                                                    -VSD-IAT

                                                       👇👇👇 



  <img width="376" alt="q26" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1871e9ab-aae9-4bc4-b32b-1aada70498a3">

                                                                                                                                                                    -VSD-IAT

*  (⊖+1+2)<(T+1+3+4)

   (⊖+Δ1)<(T+Δ2)-S-SU

  <img width="367" alt="q27" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4e9896c3-8629-4516-b84a-2a32d08b4125">

                                                                                                                                                                    -VSD-IAT

*  Δ1-Δ2=Skew

### Assumptions

*  with, I = 1ns

*  assume, S = 10ps

            = 0.01ns

*  uncertainty = 90ps

              = 0.0ns

  (⊖+Δ1)<(T+Δ2)-S-SU

*  (⊖+Δ1)= Data arrival time

*  (T+Δ2)-S-SU= Data Required time

*  if the answer is '-', it is -Slack and

*  if it is '+', it is +Slack


## Hold timing Analysis
### Hold Analysis
 
*  here we send the single signal to both launch and capture Flop

  <img width="478" alt="q28" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/4fbe16a0-fd1e-468d-877c-4d190a33c97f">

                                                                                                                                                                    -VSD-IAT

*  internal delay is hold time

  ⊖+1+2>H+1+3+4

  ⊖+Δ1>H+Δ2+HU

*  identifying

  <img width="403" alt="q30" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a1f7b149-e032-4e37-be0c-63571f27a5f0">

                                                                                                                                                                    -VSD-IAT

  <img width="85" alt="q29" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/166a290a-c4bc-4605-a74c-04d80726a872">

                                                                                                                                                                   -VSD-IAT

*  Δ1 = Real wire RC delay1

       + Buf delay

       + Real wire RC delay2

       + Buf delay

       + Real wire RC delay3

       + Buf delay

       + Real wire RC delay4

       + Buf delay

       + Real wire RC delay5

       + Buf delay

*   Δ2 = Real wire RC delay1

       + Buf delay

       + Real wire RC delay2

       + Buf delay

       + Real wire RC delay3

       + Buf delay

       + Real wire RC delay4

       + Buf delay

       + Real wire RC delay5

       + Buf delay


## Lab pictures


<img width="209" alt="ll" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e6b796d4-5807-4295-b951-a978711248d5">

                                                                                                                                                                    -VSD-IAT

<img width="115" alt="ll1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/8e87cfee-9e70-4dba-b491-a068f202ab12">

                                                                                                                                                                    -VSD-IAT

<img width="153" alt="ll2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a0db6b65-48bc-428e-bed2-4a837a56953c">

                                                                                                                                                                    -VSD-IAT

<img width="344" alt="ll3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/8960ea13-7426-427b-b167-a306b4ec9373">

                                                                                                                                                                    -VSD-IAT

<img width="220" alt="ll4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/8fdcb020-8314-4791-a85d-c9816cf833c4">

                                                                                                                                                                    -VSD-IAT

<img width="131" alt="ll5" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/093535cb-fd7b-4d9f-9931-748b08878e6b">

                                                                                                                                                                    -VSD-IAT

<img width="236" alt="ll6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/5d28039c-f12f-446e-a530-01050f7d7b0b">

                                                                                                                                                                    -VSD-IAT

<img width="273" alt="ll7" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fae1ee76-5e85-4b75-ac7c-3179e0871ce6">

                                                                                                                                                                    -VSD-IAT

<img width="560" alt="ll8" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/abe810a4-49ad-4d5d-8691-b7570be4ccb0">

                                                                                                                                                                    -VSD-IAT

## Day 5 
## ROUTE
### Routing

* It means to route two things

### Maze routing

*  Lee's algorithm (Lee 1961).

* We need to route this


<img width="347" alt="r" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/b5907a2d-2d94-4c5d-9d36-9efa6a10924f">

                                                                                                                                                                    -VSD-IAT

* Then create routing at back end


<img width="345" alt="r1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/9d3eb900-a355-420c-9825-0f10b675104f">

                                                                                                                                                                    -VSD-IAT
  
* Then create two points


<img width="347" alt="r2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/180abe93-f0d4-4d6e-8af2-627c8aefcfaf">

                                                                                                                                                                    -VSD-IAT

* Then it does the numbering to reach the target 



 <img width="355" alt="r3" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7860ef8f-9350-4600-a13f-d40079095796">
 
                                                                                                                                                                    -VSD-IAT
 
* Then make the route 



<img width="350" alt="r4" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e409e68a-e2ef-45b9-9de8-b6511c2ccefc">
    
                                                                                                                                                                    -VSD-IAT
  
* But it favours the least / single L 



<img width="361" alt="r5" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d7f82fe2-5519-4264-a69f-9c0075d6765a">

                                                                                                                                                                   -VSD-IAT 

### DRC Clean

* Whenever we build a wire, there should be a min distance between other wires


<img width="554" alt="r6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a6747735-4835-4cd7-b0a5-5c057e00c841">
  
                                                                                                                                                                    -VSD-IAT
  
* 3 typical design rules for the above pair of wires will be:

The wire width should be a particular size (X)

The min pitch between two wires should be particular (X)

The min placing between the two wires should be particular (X)
  
* For example :

We have this oicture as an example :


<img width="549" alt="r7" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6f86bc42-5631-4405-bf88-f0e2ab629267">

                                                                                                                                                                  -VSD-IAT  

* DRC Violation type signal short (Problem) 

Assume the metal layer to be Mn 

There will be a shield called Mn + 1

<img width="561" alt="r8" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/1ff7518d-5bc9-4d1c-9f39-13e462caa815">
  
                                                                                                                                                                    -VSD-IAT

Now the problem is solved - there is no signal short

The second problem is that the metal should be connected to higher metal layer and lower metal layer, this is called Via width 


  <img width="572" alt="r9" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/b3aedb75-0d45-45f0-ae15-d59f73715c01">

                                                                                                                                                                    -VSD-IAT

The third problem is that the space between the metal should be particular about size. This problem is called via spacing


<img width="552" alt="r10" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/128d047e-4157-4936-8429-19524856ed03">

                                                                                                                                                                   -VSD-IAT

## Routing using Tritan-Route
### Types of routing

*  Routing = Fast Route

*  Routing = Detailed Route


<img width="529" alt="r11" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/6f5ea2bb-f9f7-4b91-aff8-43c4852a3044">

                                                                                                                                                                    -VSD-IAT

### Steps to do and information, features

*  Performs inital detailed route

*  Honors the preprocessed route guides, attempts as much as possible to route within route guide

*  Assumes the route guides for each net satisfies the inter-guide connectivity

*  Works on preprocessed MILP-based panel routing scheme with intra-layer parallel and inter-layer sequential routing framework.

### Pre-processed route guides

  <img width="420" alt="r12" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/848ebc3f-eb34-4151-8718-87f52ae7ade1">

                                                                                                                                                                    -VSD-IAT

* Requirements of pre-processed guides :

* Should have unit width

* Should be in the pre preferred direction


### Inter-guide connectivity

* Two guides are connected if:

* They are on the same metal layer touching the edges

* They are on the neighbouring metal layers with a non-zero vertically overlapped area.

* Each unconnected terminal i.e. pin of a standard-cell instance should have its pin shape overlapped by a route guide 


### Intro-layer parallel inter-layer sequential panel routing. 

<img width="397" alt="r13" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c88d227b-a06c-4c57-832c-eacc816fe32d">

                                                                                                                                                                    -VSD-IAT

## Tritan routing
### Problem statement

*  Input : LEF, DEF, Preprocessed route guide

*  Output: Detailed routing solution with optimized wire length and via count

*  Constraints: Route guide honoring, connectivity constraints and design routes.

### Handling connectivity


<img width="365" alt="r14" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/d9b0123c-50d8-4518-a824-b7d60374a71d">

                                                                                                                                                                   -VSD-IAT

* Access Point (AP) : An ongrid point on the metal layer of the route guide and is used to connect to lower-layer segment, upper layer segments , pino or 10 points

* Access Point Cluster (APC) : A union of all APS derived from the same lower-layer segment, upper-layer guide, a pin or a 10 point.



## Routing topology algorithm
### Algorithm 1.0 Optimization of routing topology

* For all i = 1 to n-1 do

* For all j = i+1 to n do

* cost(i.j) <- ( APC.i , APC.j)

* end for

* end for

* T <- MST(APC.s, COST.s)

* Return e(i.j) ∈ T





















  


































  


  



  



  

  

 
    

  
  



  



  












  



