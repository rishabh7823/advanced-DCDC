## processor/chip 
<img width="406" alt="Screenshot 2024-03-23 121603" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/939d9f5e-9961-4974-8d35-13003d2ce4b7">

                                                                                                                                                                  -VSD-IAT 
                                                                                                                                                                  
                                                                                                                                                                  
                                                                                                                                                                  
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

PADS is something from which you can send the signals inside the chip 

2-*CORE* 

CORE is something where all our digital logic are placed 

3-*DIE* 

DIE is the size of the chip which is manufactured on the silicon 


### **Working inside the chip**

1.The typical chip/core consist of RISCV SoC,SRAM,PILL,adc,adc1,dac,SPI

2.The SRAM ,PILL,adc,adc1,dac are called as foundry IP's

3.The RISCV SoV and SPI are called Macros 


### **Foundry IP's**

1.example of Foundry IP's is Rath 150

2.Foundry is basically a set of machines/a big factory and we communicate with the factory as a VLSI engineer.

3.IP is bassically called intelligent property which means it needs some extra intelligence to build this.


### **Macros**

1.Macros are digital logic and needs IP's 

### RISC-V Instruction Set Architecture {ISA}
* If we want to transfer a C code to a computer/hardware.Its first made to a assembly language program/RISC-V assembly language and then to machine language program/binary program language then its passed to the layout.
* we have to implement RISC-V specification to some RTC and then to the layout.

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
    
    **Minor work** -
    * low level system function
    * handle IO operations
    * Alocate memory

### Compiler 
* converts the languages into instructions.
* the instructios will be in chips format.

### Assembler 
* It converts the instructions into the binary language.

### Abstract interface 
* The instructions act act like the abstract interface between the language and the hardware.
* It is also called as Instruction Set Architecture or Architecture of computer

### Understanding of hardware
* The binary is sent to a RTL which will convert the binary into gate level understanding
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
* Collection of files used to make the EDA
* Process design rules:DRC,LVS,PEX
* Device models
* Digital stantard cell libraries
* I/O libaries

### Formation of PDK
* Google singed a agreement with skywater to make a PDK of 13nm and it was lounched on june 30 2020 and was the first ever open source PDK.

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
* Converts RTL to a circuit out of components from the standard cell library {SCL} 
* Basically it converts the RTL into gate levels netes
* 'Standard cells' have regular layouts
* Each has different views
-Electrical,HDL,SPICE
-Layout

### FP+PP
* It bassically means floring the chip
* Chip floor - planning : partition the chip die between different system building blacks and place the I/O pads
* Macro floor planning : we difine Dimensions,Pin location,raw definition
* Power planning : The chip is powered by VCC,VDD and they are connected to each other.they use upper metal layers hence have less resistance

### Place 
* Place the cells on the floor plan rows,aligned with the sites are placed near to each other to low the resistance
* usually done in 2 steps : Global,Detailed
* Global terris to find optinal positions for all cells and the cells could overlap
* Detailed are mininally alterd and the cells does not overlap

### Clock tree synthesis
* create a clock distribution network
* To deliver the clock to all sequention elements
* with minimum skew
* and in a good shape
* usually a tree

### Routing
* Implement the interconnect using the available metal layer
* The first one is made by titanium and other are aluminium
* metal tracks form a routing grid
* Routing grid is huge
* Divide and conquer
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
* Maain Goal: Produce a clean GDSIL with no human interaction
  
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
  
  Interactive:can operate commands and steps one on one

* Design space exploration
  
  Find the best set of flow configurations used to find sets block of figurations
  
  large number of design example
  
  43 design with their best configuration

### actual openlane ASIC flow

 <img width="590" alt="Screenshot 2024-03-26 090801" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/0fea7ae3-2e5c-4fe9-86df-4932b1525d6a">

                                                                                                                                                                    -VSD-IAT
Openlane is based on several open sources 

open sources like : OpenROAD,Yosys,ABC,Fault 

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
  
  Automatic test pattern Generation{ATPG}
  
  Fault coverge
  
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

  reactive ion etching causes chare to accumalate on the wire

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



<img width="287" alt="Screenshot 2024-03-26 130232" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/08ce3914-ebf1-434f-bb45-d8212801d2c8">





<img width="287" alt="Screenshot 2024-03-26 151732" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/c75e7b8d-0864-484e-a545-5a86ad051f0b">



![Screenshot 2024-03-31 124408](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/3d8e8873-c7ec-4e13-b051-d420cf926229)

  



                                                                                                                                                                  -all by me

