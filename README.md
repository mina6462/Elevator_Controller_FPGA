🏢 Elevator Controller — FPGA (Verilog)

A fully synthesized elevator controller implemented on an FPGA using Verilog, built around a Moore Finite State Machine architecture.


Overview
This project implements a multi-floor elevator controller on an FPGA board using Verilog HDL in Xilinx Vivado. The controller manages floor requests, door timing, and directional movement logic using a structured Moore FSM design. The project includes full simulation with testbenches, timing diagram validation, and physical I/O mapping via constraint files.

Tech Stack
CategoryTools / ComponentsLanguageVerilog HDLIDE / ToolchainXilinx VivadoTarget HardwareFPGA (Xilinx)Design PatternMoore Finite State Machine (FSM)VerificationTestbenches, Timing Diagrams

FSM Overview
The Moore FSM design separates output logic from state transitions, ensuring predictable, glitch-free behavior across all elevator states.
States include:
StateDescriptionIDLEElevator waiting, no requestsMOVING_UPTraveling to a higher floorMOVING_DOWNTraveling to a lower floorDOOR_OPENDoors open at requested floorDOOR_CLOSEDoors closing before next move

Project Structure
elevator-controller-fpga/
├── src/
│   ├── elevator_controller.v    # Top-level FSM module
│   ├── floor_request.v          # Floor request handler
│   └── door_control.v           # Door timing module
├── sim/
│   └── elevator_tb.v            # Testbench for simulation
├── constraints/
│   └── elevator.xdc             # FPGA pin mapping constraint file
├── docs/
│   ├── timing_diagram.png       # Waveform output from simulation
│   └── fsm_diagram.png          # State transition diagram
└── README.md

Key Features

Moore FSM Architecture — Clean separation of state logic and output for reliable, testable behavior
Modular Verilog Design — Separate modules for floor requests, door control, and top-level FSM
Full Testbench Coverage — Simulated all state transitions and edge cases
Constraint File Mapping — Mapped I/O signals to physical FPGA pins for hardware deployment
Timing Diagram Validation — Verified correct signal behavior using Vivado's waveform viewer


How to Run (Vivado)

Clone this repo and open Xilinx Vivado
Create a new project and add all .v files from /src as design sources
Add elevator_tb.v from /sim as a simulation source
Add elevator.xdc from /constraints as a constraint file
Run Behavioral Simulation to view waveforms
Run Synthesis → Implementation → Generate Bitstream to deploy to FPGA


Project Status
✅ Completed — October 2025 – December 2025

Media

📷 Timing diagrams and FSM state chart coming soon


What I Learned

Designing hierarchical Verilog modules for a real-world control application
Implementing and verifying Moore FSMs with full testbench coverage
Using Xilinx Vivado for the complete FPGA design flow: simulation → synthesis → bitstream
Mapping digital logic designs to physical hardware via constraint files
