# RISC-V Assembler & Simulator

Converts RISC-V assembly to 32-bit machine code.

## Usage

```bash
python Assembler.py input.txt output.txt
```

**Input:** Assembly instructions
```assembly
lw a4, 30(s3)
add s2, s3, s4
beq zero, zero, 0
```

**Output:** 32-bit binary strings
```
00000001111010011010011100000011
00000000101010011000100100110011
00000000000000000000000001100011
```

## Supported Instructions

- **R-type:** add, sub, and, or, slt, srl
- **I-type:** addi, jalr, lw
- **S-type:** sw, sh, sb
- **B-type:** beq, bne
- **J-type:** jal

## Features

- Label support (auto-calculates offsets)
- Standard RISC-V register names (a0-a7, t0-t6, s0-s11, etc.)
- Hex/binary immediates (0x1A, 0b1010)
- Two's complement encoding
- Syntax validation

## Encoding

- **R:** funct7 | rs2 | rs1 | funct3 | rd | opcode
- **I:** imm[12] | rs1 | funct3 | rd | opcode
- **S:** imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode
- **B:** imm[12|10:5] | rs2 | rs1 | funct3 | imm[4:1|11] | opcode
- **J:** imm[20|10:1|11|19:12] | rd | opcode



---

**CO Project | IIIT Delhi **
