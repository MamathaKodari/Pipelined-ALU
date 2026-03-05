# Pipelined ALU Design in Verilog

## Overview

This project implements a **3-stage pipelined Arithmetic Logic Unit (ALU)** using **Verilog HDL**.
The design separates the ALU operation into multiple stages to improve performance and throughput.

The pipeline consists of the following stages:

1. **Operand Fetch Stage**
2. **Execute Stage**
3. **Output / Write Back Stage**

The design also includes **testbenches for simulation** to verify correct ALU functionality.

## Features


* 3-stage pipelined architecture
* Modular Verilog design
* Clock driven synchronous design
* Reset functionality
* Testbench for verification
* Compatible with **Xilinx Vivado simulator**


## Pipeline Architecture

### Stage 1 – Operand Fetch

This stage receives input operands and opcode from the register inputs and forwards them to the execution stage.

Inputs:

* `reg_data1`
* `reg_data2`
* `opcode`
* `valid`

Outputs:

* `A_out`
* `B_out`
* `opcode_out`
* `valid_out`



### Stage 2 – Execute

This stage performs the required **ALU operation** based on the opcode.

Inputs:

* `A_in`
* `B_in`
* `opcode_in`
* `valid_in`

Outputs:

* `result_out`
* `valid_out`

Typical ALU operations may include:

* Addition
* Subtraction
* AND
* OR
* XOR
* Shift operations


### Stage 3 – Output / Writeback

This stage stores the final ALU result and forwards it to the output interface.

Inputs:

* `result_in`
* `valid_in`

Outputs:

* `final_result`
* `final_valid`


## Module Description

### final_alu.v

Top level module connecting all pipeline stages.

### fetch.v

Handles operand fetching and passes operands to the execution stage.

### execute.v

Performs ALU operations based on opcode.

### out.v

Stores the final result and provides output signals.

### tb_pipelined_alu.v

Testbench used to simulate and verify the pipelined ALU design.

## Simulation

### Steps to Run in Vivado

1. Open **Vivado**
2. Create a **New RTL Project**
3. Add all Verilog design files
4. Add testbench files
5. Set `tb_pipelined_alu.v` as **top simulation module**
6. Run **Run Simulation → Run Behavioral Simulation**


## Example Test Case

| A  | B | Opcode | Operation   | Result |
| -- | - | ------ | ----------- | ------ |
| 7  | 2 | 000    | Addition    | 9      |
| 10 | 5 | 001    | Subtraction | 5      |
| 15 | 3 | 010    | AND         | 3      |


## Applications

* Processor datapath design
* Digital system design
* High-performance ALU architectures
* Computer architecture learning


## Author

MamathaKodari/ECE/Pipelined-ALU


## License

This project is for **educational and academic purposes**.
