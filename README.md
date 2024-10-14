Aim
To design and simulate a seven-segment display driver using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 environment. The objective is to implement the logic that converts a 4-bit binary input into the corresponding 7-segment display output for the digits 0 to 9.

Apparatus Required
Vivado 2023.1
Computer system with a suitable operating system.

Procedure

Launch Vivado 2023.1:

Open Vivado and create a new project.
Design the Verilog Code:

Write the Verilog code for the seven-segment display, defining the logic that maps a 4-bit binary input to the corresponding segments (a to g) of the display.
Create the Testbench:

Write a testbench to simulate the seven-segment display behavior. The testbench should apply various 4-bit input values and monitor the corresponding output on the seven-segment display.
Add the Verilog Files:

Add both the design module and the testbench in the Vivado project.
Run Simulation:

Run the behavioral simulation to verify the output. Ensure the seven-segment display behaves correctly for binary inputs 0000 to 1001 (decimal 0 to 9).
Observe the Waveforms:

Analyze the output waveforms in the simulation window, and verify that the correct segments light up for each digit.
Save and Document Results:

Capture screenshots of the waveform and save the simulation logs. These will be included in the lab report.

Diagram

![image](https://github.com/user-attachments/assets/d7ecb419-906e-4e3b-9b82-f86ced4f364a)


Verilog Code for Seven-Segment Display

module sevensegment(seg,s);

input [3:0]seg;

output reg[6:0]s;

always @(seg)

begin

case(seg)

4'd0:s=7'b0111111;4'd1:s=7'b0000110;

4'd2:s=7'b1011011;

4'd3:s=7'b1001111;

4'd4:s=7'b1100110;

4'd5:s=7'b1101101;

4'd6:s=7'b1111101;

4'd7:s=7'b0000111;

4'd8:s=7'b1111111;

4'd9:s=7'b1101111;

default:s=7'b0000000;

endcase

end
endmodule

Testbench for Seven-Segment Display:

module sevensegment_tb;

reg [3:0]seg;

wire [6:0]s;

sevensegment dut(seg,s);

initial 

begin

seg=4'd0;

#100

seg=4'd1;

#100

seg=4'd2;

#100

seg=4'd3;

#100

seg=4'd4;

#100

seg=4'd5;

#100

seg=4'd6;

#100

seg=4'd7;

#100

seg=4'd8;

#100

seg=4'd9;

end

endmodule

Ouput :
![image](https://github.com/user-attachments/assets/6f8f8393-5f90-4a0a-9b29-f8d087e7f11f)




Conclusion

In this experiment, a seven-segment display driver was successfully designed and simulated using Verilog HDL. The simulation results confirmed that the display correctly represented the digits 0 to 9 based on the 4-bit binary input. The testbench effectively verified the functionality of the seven-segment display by applying various input combinations and observing the corresponding segment outputs. This experiment highlights how Verilog HDL can be used to control hardware components like a seven-segment display in digital systems.
