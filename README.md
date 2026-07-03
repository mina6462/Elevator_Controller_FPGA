🏢 Elevator Controller — FPGA (Verilog)

This project revolved around utilizing Verilog code within Xilinx Vivado to physically code the hardware of the Nexys A7 FPGA board. The purpose was to create an elevator controller simulator, where the current and desired floor states could be shown via the seven-segment displays on the board. The manual inputs were generated through the physical pushbuttons, and reset + emergency states were included for safety purposes.

One of the main challenges throughout this project was the timing of the system. When simulating the timing diagram, the state of the desired and current floors was seen to continually have issues. This was due to the overall logic of the Verilog code, which required modification of the state diagram. The current state must be updated every second to reflect changes in floors, while the desired floor must remain consistent until a new floor is selected once the desired floor has been reached. 

In order to utilize a delay within the system, a clock timer module was created for one second. Since the system runs at 50MHz, the frequency was utilized such that the system would count 50 million cycles, and once this value was reached, it would toggle the delay value. Since we are programming the hardware, this is a unique strategy to incorporate a delay within the code once this module unit is called. 

Therefore, the hierarchical design within a top module allowed for the importance of FInite state machines and manipulating hardware to be understood.
