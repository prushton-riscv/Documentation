```
 31         27 26       21 20  16 15  11 10   6 5      0
+-------------+-----------+------+------+------+--------+
|    funct    |   imm     |  rs2 |  rs1 |  rd  | opcode | R-Type //register based instructions (rd = rs + rt)
+-------------+-----------+------+------+------+--------+
//imm represents offset of rd when using for lw

 31         27 26              16 15  11 10   6 5      0
+-------------+------------------+------+------+--------+
|    funct    |         imm      |  rs1 |  rd  | opcode | I-Type //immediate based instructions (rd = imm + rt)
+-------------+------------------+------+------+--------+

 31         27 26      21 20   16 15  11 10   6 5      0
+-------------+----------+-------+------+------+--------+
|    funct    |          |  rs2  |  rs1 |  rd  | opcode | S-Type //Save word instructions //wtf is going on here
+-------------+----------+-------+------+------+--------+
```
Since a lot of risc processors tend to be 32 bit, I decided to make mine 64 bit. This would give me more room for registers, memory addresses, opcodes, funct codes, etc. Perhaps I could make the opcode a 1:1 corresponding to the bits?
# 32 Bit
## R type Instruction
| 31 - 27 | 26 - 21 | 20 - 16 | 15 - 11 | 10 - 6 | 5 - 0 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| funct | imm | rs2 | rs1 | rd | opcode |

## I Type
| 31 - 27 | 26 - 16 | 15 - 11 | 10 - 6 | 5 - 0 |
| ---- | ---- | ---- | ---- | ---- |
| funct | imm | rs1 | rd | opcode |

## S Type
| 31 - 27 | 26 - 16 | 15 - 11 | 10 - 6 | 5 - 0 |
| ---- | ---- | ---- | ---- | ---- |
| funct | offset | rs | md | opcode |

## J Type
| 31 - 27 | 26 - 16 | 15 - 11 | 10 - 6 | 5 - 0 |
| ---- | ---- | ---- | ---- | ---- |
| funct |  |  |  | opcode |

# 64 Bit

## R Type
| 63 - 54 | 53 - 42 | 41 - 32 | 31 - 22 | 21 - 12 | 11 - 0 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| funct | imm | rs2 | rs1 | rd | opcode |

## I Type
| 63 - 54 | 53 - 32 | 31 - 22 | 21 - 12 | 11 - 0 |
| ---- | ---- | ---- | ---- | ---- |
| funct | imm | rs1 | rd | opcode |

## S Type
| 63 - 54 | 53 - 32 | 31 - 22 | 21 - 12 | 11 - 0 |
| ---- | ---- | ---- | ---- | ---- |
| funct | offset | ra | da | opcode |
`sa` is the addressed source, `da` is the addressed destination. They can be either memory or registers depending on the instruction1