# ALU with Register File — Verilog Implementation

An 8×8-bit register file integrated with a combinational ALU, supporting single-port write, dual-port read, and 10 arithmetic/logic operations selected via a 4-bit opcode.


## Overview

This project implements a small register file (8 registers, 8 bits wide) tightly coupled with a combinational ALU. The register file supports a single write port and two simultaneous read ports (R1, R2), and the values read out are fed directly into the ALU, which computes a result c based on a 4-bit opcode (sel). This mirrors the register-file-to-ALU datapath found in simple RISC-style processors, making it a useful stepping stone toward a full single-cycle CPU design.

## Tools 

- Xilinx Vivado 
- Verilog HDL

## architecture
~~~
addr, in, readwrite, enable
                    │
                    ▼
        ┌──────────────────────┐
        │   Register File      │
        │   8 x 8-bit regs     │
        │  (1 write, 2 read)   │
        └───────┬───────┬──────┘
                R1      R2
                 │       │
                 ▼       ▼
            ┌───────────────┐
     sel───►│      ALU       │───► c
            └───────────────┘
~~~
## Features

8 general-purpose 8-bit registers with independent write and dual-read addressing
Single shared readwrite control line for compact decode logic
Asynchronous reset for deterministic register-file initialization
10 ALU operations selected by a 4-bit opcode

## Future Improvements
- Add overflow and carry flag support.
- Parameterize the ALU width (8-bit, 16-bit, 32-bit).
- Implement signed arithmetic operations.
- Extend functionality with rotate and increment/decrement operations.
- 
## Report

- design.v          # Register file + ALU RTL
-  Test_bench.v        # Testbench
-  README.md           # This file
