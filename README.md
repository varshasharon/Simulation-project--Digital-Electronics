# TITLE
Design and simulate mod 3 synchronous counter using Verilog.
# THEORY
A mod 3 synchronous counter is a digital circuit that counts in modulo-3 sequence, meaning it counts from 0 to 2 and then resets to 0. 
We can implement this counter using JK flip-flops.
# LOGIC DIAGRAM
![image](https://github.com/varshasharon/Simulation-project--Digital-Electronics/assets/98278161/94dd9e63-b634-4104-a2f9-2627f8c78416)

# PROCEDURE
We have a module called "Mod3Counter" with inputs "clk" (clock) and "reset", and an output "count" of 3 bits representing the counter value.

The counter is implemented using a synchronous always block, which triggers on the positive edge of the clock signal or the positive edge of the reset signal.

Inside the always block, we have a case statement that checks the current value of the "count" register and updates it accordingly. When the reset signal is active (high), the counter is reset to 0. Otherwise, the counter value is incremented modulo 3, meaning it goes from 0 to 2 and then resets to 0 again.

# PROGRAM
```
Program developed by
NAME: E. VARSHA SHARON
REGISTER NO: 212222100058

module syncs(clk,reset,count);
  input clk;
  input reset;
  output reg [1:0] count;
  always @(posedge clk or posedge reset) 
  begin
    if (reset)
      count <= 2'b00;
    else begin
      case (count)
        2'b00: count <= 2'b01;
        2'b01: count <= 2'b10;
        2'b10: count <= 2'b00;
        2'b11: count <= 2'b00;
      endcase
    end
  end
endmodule
```

# TIMING DIAGRAM
![simu 1](https://github.com/varshasharon/Simulation-project--Digital-Electronics/assets/98278161/48a329c1-b5e7-4aed-b428-f99c7842354b)

# RTL VIEWER

![simu 2](https://github.com/varshasharon/Simulation-project--Digital-Electronics/assets/98278161/f83f6eec-d8e1-4d14-81d0-a7d22bf1348b)

# RESULT
Thus the program to design and simulate mod 3 synchronous counter using verilog was executed successfully.


