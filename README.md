# Synchronous_Up_Counter1


**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */


**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:P.Abinaya RegisterNumber:25014594
*/
```
module synchronousupcounter (
    input  wire clk,       // clock input
    input  wire rst,       // synchronous reset
	 input  wire d,
    output reg  [2:0] q   // 3-bit counter output
);

initial begin
     q <= 3'b0000;
	 end

always @(posedge clk) 
begin
q <= 3'b000;
    if (rst) 
        q <= 3'b000;       // reset counter to 0
    else if(d)
        q <= q + 1;        // increment counter
		  else
		  q <= q - 1;
end

endmodule
```

**RTL LOGIC UP COUNTER**
<img width="1896" height="910" alt="Screenshot 2025-12-14 100522" src="https://github.com/user-attachments/assets/d259497b-3958-4038-ad57-8d073948310b" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="637" height="356" alt="Screenshot 2025-12-14 100822" src="https://github.com/user-attachments/assets/246d68d6-1d11-41f3-ba9e-ff22718bebc6" />

**TRUTH TABLE**

**RESULTS**
