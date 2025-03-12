# Processor Architecture Design using RISC-V

## Overview
This project involves the design and implementation of a RISC-V processor in Verilog. The processor supports both sequential and pipelined architectures, demonstrating instruction execution efficiency.

## Features
- **Sequential Execution:** Implements a simple single-cycle processor where each instruction goes through fetch, decode, execute, memory access, and write-back stages sequentially.
- **Pipelined Execution:** Implements a 5-stage instruction pipeline to enhance throughput and efficiency.
- **Forwarding and Hazard Detection:** Implements techniques to handle data and control hazards in the pipelined design.
- **Memory Management:** Supports memory read/write operations with address validation.

## Processor Architecture
### **1. Sequential Execution**
- **Fetch:** Retrieves the instruction from memory.
- **Decode:** Identifies the operation and fetches operands.
- **Execute:** Performs ALU operations.
- **Memory:** Handles load/store operations.
- **Write Back:** Writes the result back to registers.

### **2. Pipelined Execution**
The pipeline consists of the following stages:
- **IF (Instruction Fetch):** Fetches the instruction and updates PC.
- **ID (Instruction Decode):** Decodes the instruction and fetches operands.
- **EX (Execute):** Performs ALU operations and computes branch targets.
- **MEM (Memory Access):** Handles memory operations.
- **WB (Write Back):** Updates register values with execution results.

## Implementation Details
- **Hazard Handling:**
  - **Data Hazards:** Resolved using forwarding and pipeline stalls.
  - **Control Hazards:** Managed through branch prediction and flushing.
- **Pipeline Registers:**
  - IF/ID, ID/EX, EX/MEM, MEM/WB to store intermediate results.

## Challenges Faced
- Correcting PC updates for branch instructions.
- Handling sign-extension for immediate values.
- Implementing hazard detection and stall insertion.

## Files Included
- `sequential/` - Contains Verilog files for sequential processor implementation.
- `pipelined/` - Contains Verilog files for pipelined processor.

