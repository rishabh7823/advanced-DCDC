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

* Whenever we build a wire, there should be a minimum distance between other wires


<img width="554" alt="r6" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/a6747735-4835-4cd7-b0a5-5c057e00c841">
  
                                                                                                                                                                    -VSD-IAT
  
* 3 typical design rules for the above pair of wires will be:

The wire width should be a particular size (X)

The minmum pitch between two wires should be particular (X)

The minmum placing between the two wires should be particular (X)
  
* For example :

We have this picture as an example :


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

## LAB pictures

<img width="602" alt="kk" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/e53ea9b1-2d72-4693-b206-b18d5f804003">

                                                                                                                                                                  

<img width="412" alt="kk1" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/ee9187dc-45e4-4107-8014-af9a70a9d02e">

                                                                                                                                                                           
                                                                                                                                                                   
<img width="101" alt="kk2" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/67c8bebf-8ac6-4213-b374-8bdd2bbb5713">
                                                                                                                                                                   
                                                                                                                                                                  
 
<img width="584" alt="-" src="https://github.com/rishabh7823/advanced-DCDC/assets/164547532/462ea639-0cb2-4623-8dbb-bd88fa11938f">

![WhatsApp Image 2024-03-31 at 21 25 26_3bba8154](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/df8e3ac0-78bb-471f-bcfc-4251c499fb1a)
                                                                                                                                                                  
![WhatsApp Image 2024-03-31 at 21 28 08_d3ba3c14](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/90b20c5c-fceb-4af4-a617-a5b319097305)

![WhatsApp Image 2024-03-31 at 22 10 37_3234a329](https://github.com/rishabh7823/advanced-DCDC/assets/164547532/11047a88-a9e8-4a6e-a863-db62545de113)

                                                                                                                                                                  -All by me
