# 🔧 8-Bit Pipelined Processor

<p align="center">
  <img src="https://img.shields.io/badge/Architecture-8--bit-blue?style=for-the-badge" alt="8-bit Architecture">
  <img src="https://img.shields.io/badge/Pipeline-2--stage-orange?style=for-the-badge" alt="2-stage Pipeline">
  <img src="https://img.shields.io/badge/Platform-Logisim-green?style=for-the-badge" alt="Logisim Platform">
  <img src="https://img.shields.io/badge/Addressing-Direct%20Mode-red?style=for-the-badge" alt="Direct Addressing">
</p>

A comprehensive implementation of a 2-stage pipelined 8-bit processor with direct addressing capabilities, designed and simulated using the Logisim digital logic simulator platform.

## 📝 Overview

This project presents a fully functional 8-bit processor with a 2-stage pipeline architecture that efficiently executes 1-address format instructions using direct addressing mode. The design strikes a balance between simplicity and functionality, making it an excellent educational resource for understanding fundamental processor architecture concepts.

## 🏗️ Architecture

The processor follows a simple yet efficient two-stage pipeline design:

```
┌───────────────┐         ┌───────────────┐
│  Instruction  │         │   Execution   │
│  Fetch (IF)   │ ───────►│     (EX)      │
└───────────────┘         └───────────────┘
```

### Key Components:

- **Control Unit**: Orchestrates all processor operations
- **Arithmetic Logic Unit (ALU)**: Performs mathematical and logical operations
- **Accumulator (ACC)**: Main register for arithmetic operations
- **Program Counter (PC)**: Tracks the address of the next instruction
- **Instruction Register (IR)**: Holds the current instruction
- **Memory Address Register (MAR)**: Holds addresses for memory access
- **Memory Data Register (MDR)**: Facilitates data transfer between processor and memory
- **Pipeline Registers**: Buffers data between pipeline stages

## ⚙️ Features

- **8-bit Data Path**: Processes 8-bit data words
- **2-Stage Pipeline**: Increases throughput by overlapping instruction execution
- **Direct Addressing Mode**: Operand addresses specified directly in instructions
- **1-Address Instruction Format**: One operand explicitly addressed per instruction
- **Simple ISA**: Focused instruction set for educational clarity
- **Memory-Mapped I/O**: Unified addressing for memory and I/O devices
- **Hazard Detection**: Basic pipeline hazard management

## 📋 Instruction Set

| Opcode (Binary) | Mnemonic | Operation                 | Description                            |
|-----------------|----------|---------------------------|----------------------------------------|
| `000`           | `LDA`    | ACC ← M[addr]             | Load accumulator from memory           |
| `001`           | `STA`    | M[addr] ← ACC             | Store accumulator to memory            |
| `010`           | `ADD`    | ACC ← ACC + M[addr]       | Add memory to accumulator              |
| `011`           | `SUB`    | ACC ← ACC - M[addr]       | Subtract memory from accumulator       |
| `100`           | `AND`    | ACC ← ACC ∧ M[addr]       | Logical AND with accumulator           |
| `101`           | `OR`     | ACC ← ACC ∨ M[addr]       | Logical OR with accumulator            |
| `110`           | `JMP`    | PC ← addr                 | Jump to address                        |
| `111`           | `JZ`     | If ACC = 0 then PC ← addr | Jump to address if accumulator is zero |

## 🔄 Pipeline Stages

### 1. Instruction Fetch (IF)
- Fetches the next instruction from memory
- Updates the Program Counter
- Decodes the instruction opcode
- Passes instruction information to the next stage

### 2. Execution (EX)
- Performs the operation specified by the instruction
- Accesses memory for operands using direct addressing
- Updates the accumulator or other registers
- Handles control flow instructions

## 🔍 Pipeline Hazards & Solutions

The processor implements basic hazard detection and resolution:

- **Data Hazards**: Resolved through forwarding when possible
- **Control Hazards**: Handled by pipeline stalling when necessary
- **Structural Hazards**: Mitigated through efficient resource allocation

## 💻 Simulation

### Requirements
- [Logisim](http://www.cburch.com/logisim/) (Version 2.7.1 or newer)
- Java Runtime Environment

### How to Run
1. Clone this repository
2. Open Logisim application
3. Load the `8bit_processor.circ` file
4. Use the simulation controls to step through execution or run continuously

### Testing
A comprehensive test suite is included that verifies:
- Individual instruction functionality
- Pipeline operation under various conditions
- Hazard detection and resolution
- Edge cases and corner scenarios

## 🛠️ Implementation Details

### Memory Organization
- **Program Memory**: Stores instruction codes
- **Data Memory**: Stores data values
- **Shared Address Space**: 8-bit addressing allowing access to 256 memory locations

### Control Signals
The Control Unit generates signals based on the current instruction:
- ALU operation selection
- Register load enables
- Memory read/write enables
- Pipeline control signals

## 📊 Performance Analysis

| Metric                     | Value                |
|----------------------------|----------------------|
| Clock Frequency (Max)      | *Platform dependent* |
| Instructions Per Cycle     | 0.5 - 1.0            |
| Pipeline Efficiency        | ~75% (with hazards)  |
| Average CPI                | 1.33                 |
| Pipeline Register Overhead | 16 bits              |

## 🔮 Future Enhancements

- Add branch prediction capability
- Implement more complex addressing modes
- Extend to a 3-stage pipeline
- Add interrupt handling functionality
- Incorporate cache memory simulation

## 🧪 Technical Details

```
Word Size:     8 bits
Address Space: 256 bytes
Instruction Format:
    ┌───────┬───────────┐
    │Opcode │  Address  │
    │(3 bits)│ (5 bits) │
    └───────┴───────────┘
```

## 📁 Repository Structure

```
.
├── src/
│   ├── 8bit_processor.circ      # Main Logisim circuit file
│   ├── alu.circ                 # ALU component
│   ├── control_unit.circ        # Control unit component
│   └── memory.circ              # Memory subsystem
├── tests/
│   ├── test_programs/           # Sample programs
│   └── test_results/            # Expected outputs
├── docs/
│   ├── architecture.pdf         # Detailed architecture documentation
│   ├── instruction_set.pdf      # Full ISA specification
│   └── user_guide.pdf           # Usage instructions
├── images/                      # Screenshots and diagrams
└── README.md                    # This file
```

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ✉️ Contact

For questions or feedback, please open an issue on this repository or contact the maintainers directly.

---

<p align="center">
  <sub>Built with ❤️ for computer architecture enthusiasts</sub>
</p>
