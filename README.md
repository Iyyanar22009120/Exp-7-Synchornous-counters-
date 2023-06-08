# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
/* write all the steps invloved */



### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: IYYANAR S
RegisterNumber:  212222240036
```

```
### UP-COUNTER:
module UC(input clk,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@ (posedge clk or posedge reset)
begin
if(reset)
counter_up <= 4'd0;
else
counter_up <= counter_up + 4'd1;
end
assign counter = counter_up;
endmodule

### DOWN-COUNTER:
module DC(input clk,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_down <= 4'd0;
else
counter_down <= counter_down - 4'd1;
end
assign counter = counter_down;
endmodule
```
## OUTPUT:
## UP-COUNTER:
## RTL Logic:
![up1](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/c30860a8-2350-43c4-9c21-579fca261a9a)

## Timing Diagram for Counter:
![up2](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/90950189-6594-4645-afd4-51f47f9412b2)
![up3](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/e5fbef8a-93e2-4e87-86bd-c4d7028d6125)

## Truth Table:
![up4](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/9962e91b-0094-4b05-8f39-2a18a789aee5)

## UP-COUNTER:
## RTL Logic:
![down1](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/dd30620d-efe0-4c9e-81fd-d4f6ea4d21e9)

## Timing Diagram for Counter:
![down2](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/9dd0ecc7-3aa7-4252-ba4c-734e04208954)
![down3](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/7feac700-0134-4a59-8d1c-0c185cd5fb27)

## Truth Table:
![down 4](https://github.com/Iyyanar22009120/Exp-7-Synchornous-counters-/assets/118680259/656d65fb-ef32-4d37-965e-1227fc18fe18)

### RESULTS 
Thus 4 bit up and down counters is implemented and its functionality is validated.
