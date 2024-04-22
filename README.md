# VLSI-LAB-EXP-4
# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

# AIM: 
 To simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters using Vivado 2023.2

# APPARATUS REQUIRED:
vivado 2023.2

# LOGIC DIAGRAM

# SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


# JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

# T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


# D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


# COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
# PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# VERILOG CODE
# SR FLIPFLOP:
module SR(clk,s,r,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

endmodule
# JK FLIPFLOP:
module jk(j,k,clk,rst,Q);

input j,k,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)Q=0;

else

begin

case({j,k})

2'b00:Q=Q;

2'b01:Q=0;

2'b10:Q=1;

2'b11:Q=~Q;

endcase

end

end

endmodule
# T FLIPFLOP:
module tff(t,clk,rst,Q);

input t,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else if(t==0)

Q=Q;

else

Q=~Q;

end

endmodule
# D FLIPFLOP:
module dff(d,clk,rst,Q);

input d,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else

Q=d;

end

endmodule
# COUNTER
# UPDOWN COUNTER:
module updown(clk,rst,updown,out);

input clk,rst,updown;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1)

out=4'b0000;

else if(updown==1);

out=out-1;

end

endmodule
# MOD 10 COUNTER:
module mod(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always @(posedge clk)

begin

if(rst==1 | out==4'b1001)

out=4'b0000;

else

out=out+1;

end

endmodule
# RIPPLE CARRY COUNTER:
module ripple_carry_counter(q, clk, reset);

output [3:0] q;

input clk, reset;

T_FF tff0(q[0], clk, reset);

T_FF tff1(q[1], q[0], reset);

T_FF tff2(q[2], q[1], reset);

T_FF tff3(q[3], q[2], reset);

endmodule

module T_FF(q, clk, reset);

output q;

input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule

module D_FF(q, d, clk, reset);

output q;

input d, clk, reset;

reg q;

always @(posedge reset or negedge clk)

if (reset)

q = 1'b0;

else

q = d;

endmodule

# OUTPUT WAVEFORM
 # SR FLIPFLOP:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/d6027591-d6fd-4e78-a7e2-2870d95d1f83)

 # JK FLIPFLOP:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/2de464cc-ce50-4cb5-be79-fa53b4baa2f6)

 # T FLIPFLOP:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/4b14fd21-817c-4e7a-b2f8-3dd10b31b57d)

 # D FLIPFLOP:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/a6a6e536-54bb-468e-aba1-121be1a187c0)

 # COUNTER:
 # UPDOWN COUNTER:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/37a67e2f-252c-4f83-97b4-8913d6376aa8)
 
 # MOD 10 COUNTER:

 ![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/8db6e747-2bf5-4aeb-975e-edcd5ef57c75)

# RIPPLE CARRY COUNTER:

![image](https://github.com/prithyusha/VLSI-LAB-EXP-4/assets/159164885/567ae86a-ea6d-4ad5-8a90-9dfe32b6c7fb)


# RESULT
Thus simulate and synthesis JK-Flipflop, SR-Flipflop, T-Flipflop, D-Flipflop And counters was succesfully executed and verified.

