# Lab2ECE128

# Adder.V
`timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date: 09/12/2023 01:40:48 PM
// Design Name: 
// Module Name: Adder
// Project Name: 
// Target Devices: 
// Tool Versions: 
// Description: 
// 
// Dependencies: 
// 
// Revision:
// Revision 0.01 - File Created
// Additional Comments:
// 
//////////////////////////////////////////////////////////////////////////////////


module Adder(
    input A,
    input B,
    input Ci,
    output reg Co,
    output reg Sum
    );
    always@(*)
   begin 
   
   case({A,B,Ci})
    3'b000:  Sum = 1'b0;
    3'b001:  Sum = 1'b1;
    3'b010: Sum = 1'b1;
    3'b011: Sum = 1'b0;
    3'b100:  Sum = 1'b1;
    3'b101: Sum = 1'b0;
    3'b110:  Sum = 1'b0;
    3'b111: Sum = 1'b1;
    endcase
    
   case({A,B,Ci})
    3'b000:  Co = 1'b0;
    3'b001:  Co = 1'b0;
    3'b010: Co = 1'b0;
    3'b011: Co = 1'b1;
    3'b100:  Co = 1'b0;
    3'b101: Co = 1'b1;
    3'b110:  Co = 1'b1;
    3'b111: Co = 1'b1;
    endcase
   end
endmodule
 
  # Adder_tb.v
  `timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date: 09/12/2023 01:49:31 PM
// Design Name: 
// Module Name: Adder_tb
// Project Name: 
// Target Devices: 
// Tool Versions: 
// Description: 
// 
// Dependencies: 
// 
// Revision:
// Revision 0.01 - File Created
// Additional Comments:
// 
//////////////////////////////////////////////////////////////////////////////////


module Adder_tb();
    reg A,B,Ci;
    wire Co,Sum;
    Adder uut0(.A(A),.B(B),.Ci(Ci),.Sum(Sum),.Co(Co));
    initial begin
        #10
        A=0;B=0;Ci=0;
        #10
        A=0;B=0;Ci=1;
        #10
        A=0;B=1;Ci=0;
        #10
        A=0;B=1;Ci=1;
        #10
        A=1;B=0;Ci=0;
        #10
        A=1;B=0;Ci=1;
        #10
        A=1;B=1;Ci=0;
        #10
        A=1;B=1;Ci=1;
        end
        
        endmodule
