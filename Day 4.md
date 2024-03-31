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
