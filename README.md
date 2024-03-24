# advanced-DCDC
## Day 1 
### processor/chip 
<img width="406" alt="Screenshot 2024-03-23 121603" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/939d9f5e-9961-4974-8d35-13003d2ce4b7">
“<img width="139" alt="Screenshot 2024-03-23 130930" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/7fe8b449-5225-49c2-9f75-27b6a92284fe">


1-This is how the processor looks like


<img width="434" alt="Screenshot 2024-03-23 133754" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/fa7375cb-275e-4b8d-b9c8-5c657fe1a509">


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

The properties needed for ASIC :-

<img width="514" alt="Screenshot 2024-03-24 123120" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/24c8460e-7e8d-467c-be2b-c0f3f243744b">

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
