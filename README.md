# 32-bit Pipelined MIPS Processor in Verilog HDL

## Overview

This project implements a 32-bit pipelined MIPS processor using Verilog HDL. The processor follows a five-stage pipeline architecture consisting of Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write Back (WB) stages.

The design supports arithmetic, logical, memory access, and branch instructions and was verified using custom testbenches and simulation waveforms.

---

## Processor Architecture

![Processor Architecture](architecture/mips32_pipeline_diagram.jpg)

The processor uses pipeline registers between stages:

* IF/ID
* ID/EX
* EX/MEM
* MEM/WB

A two-phase clocking scheme is used to control instruction flow through the pipeline.

---

## Features

* 32-bit MIPS-like processor
* Five-stage pipelined architecture
* Two-phase clocking
* 32 × 32 Register File
* 1024 × 32 Main Memory
* Branch instruction support
* Load and Store operations
* Pipeline registers between stages
* Verilog HDL implementation

---

## Supported Instructions

### Arithmetic and Logical Instructions

* ADD
* SUB
* AND
* OR
* SLT
* MUL

### Immediate Instructions

* ADDI
* SUBI
* SLTI

### Memory Instructions

* LW
* SW

### Branch Instructions

* BEQZ
* BNEQZ

### Control Instruction

* HLT

---

## Pipeline Stages

### Instruction Fetch (IF)

Fetches instructions from memory and updates the Program Counter.

### Instruction Decode (ID)

Decodes the instruction, reads register operands, and generates control information.

### Execute (EX)

Performs arithmetic, logical, branch, and address calculations.

### Memory Access (MEM)

Performs memory read and write operations.

### Write Back (WB)

Writes computation or memory results back to the register file.

---

## Verification

The processor was verified using custom Verilog testbenches.

### Example 1

Basic arithmetic instruction verification.

### Example 2

Load-Modify-Store program:

1. Load data from memory location 120
2. Add 45 to the value
3. Store the result in memory location 121

Simulation Result:

* Memory[120] = 85
* Memory[121] = 130

---

## Project Structure

```text
MIPS32-Pipelined-Processor
│
├── src
│   └── pipe_MIPS32.v
│
├── testbench
│   ├── example1_tb.v
│   └── example2_tb.v
│
├── architecture
│   └── mips32_pipeline_diagram.jpg
│
├── waveforms
│   ├── example1.png
│   └── example2.png
│
└── README.md
```

---

## Limitations

Current implementation does not include:

* Data forwarding
* Hazard detection unit
* Pipeline stalling
* Branch prediction
* Cache memory

Programs containing data dependencies may require software-inserted NOP instructions for correct execution.

---

## Tools Used

* Verilog HDL
* Icarus Verilog
* GTKWave

---

## Author

Sai Praneeth

B.Tech Electronics and Computer Engineering (ECM)
