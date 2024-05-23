 EXP-5

 DATE: 
              
               SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

**AIM:** 

To simulate and synthesis finite state machine using vivado.

**APPARATUS REQUIRED:**

  vivado 2023.2.

**PROCEDURE:**

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

**Logic Diagram :**

![331879067-237278e8-02a9-4cd7-a90f-27ad545b9464](https://github.com/durgareddy654/VLSI-LAB-EXP-5/assets/161814262/40110611-cb97-4611-bb28-369e2bff96e7)



**VERILOG CODE:**

module fsm(clk, rst, x, z);

input clk, rst, x;

output z;

reg [2:1] present_state, NEXT_STATE;

parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;

always@(x,present_state)

case(present_state)

S0: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S0;

S1: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

S2: if(x)

NEXT_STATE=S3;

else

NEXT_STATE=S0;

S3: if(x)

NEXT_STATE=S1;

else

NEXT_STATE=S2;

endcase

always@(negedge rst, posedge clk)

if(rst)

present_state<=S0;

else

present_state<=NEXT_STATE;

assign z=(present_state==S3);

endmodule



**OUTPUT:**

![331879026-af177676-d56d-4518-b949-e3692e4f4410](https://github.com/durgareddy654/VLSI-LAB-EXP-5/assets/161814262/8d824b85-3456-4038-9083-26d789111107)


**RESULT:**

Thus,the simulation and synthesis of finite state machine by using vivado has been successfully excecuted and verified.


