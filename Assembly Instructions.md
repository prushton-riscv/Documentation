See [[Assembly Structure]] for structure of instructions

### Key
* `rsx, rd` refer to register source 1 or 2 and register destination
* `imm` refers to the immediate value
* `&, *` & refers to the value cast as an address, and * refers to the value at the address

| Instruction | Type | Description | Syntax | Function | opcode | funct code |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| add | R | Add | `add rd rs1 rs2` | `rd = rs1 + rs2` | 0000_0000_0000 | 00_0000_0000 |
| sub | R | Subtract | `sub rd rs1 rs2` | `rd = rs1 - rs2` | 0000_0000_0000 | 00_0000_0001 |
| mul | R | Multiply | `mul rd rs1 rs2` | `rd = rs1 * rs2` | 0000_0000_0000 | 00_0000_0010 |
| and | R | and |  |  | 0000_0000_0000 | 00_0000_0011 |
| or | R | or |  |  | 0000_0000_0000 | 00_0000_0100 |
| xor | R | xor |  |  | 0000_0000_0000 | 00_0000_0101 |
| slt | R | set less than |  |  | 0000_0000_0000 | 00_0000_0110 |
| sgt | R | set greater than |  |  | 0000_0000_0000 | 00_0000_0111 |
| seq | R | set equals |  |  | 0000_0000_0000 | 00_0000_1000 |
| addc | R | add carry |  |  | 0000_0000_0000 | 00_0000_1001 |
| mulc | R | multiply carry |  |  | 0000_0000_0000 | 00_0000_1010 |
| lshift | R | left shift |  |  | 0000_0000_0000 | 00_0000_1011 |
| rshift | R | right shift |  |  | 0000_0000_0000 | 00_0000_1100 |
|  |  |  |  |  |  |  |
| addi | I | Add Immediate | `addi ds rs1 imm` | `rd = rs1 + imm` | 0001_0000_0000 | 00_0000_0000 |
| subi | I | Subtract Immediate | `subi rd rs1 imm` | `rd = rs1 - imm` | 0001_0000_0000 | 00_0000_0001 |
| muli | I | Multiply Immediate | `muli rd rs1 imm` | `rd = rs1 * imm` | 0001_0000_0000 | 00_0000_0010 |
|  |  |  |  |  |  |  |
| jtl | I | Jump to Label | `jtl _label` | `pc = &_label` | 0001_0000_0001 | 00_0000_0000 |
| beq | I | Branch if Equal | `beq rs1 rs2 _label` | `if(rs1 == rs2) pc = &_label` | 0001_0000_0010 | 00_0000_0000 |
| blt | I | Branch if Less Than | `blt rs1 rs2 _label` | `if(rs1 < rs2) pc = &_label` | 0001_0000_0010 | 00_0000_0000 |
| bgt | I | Branch if Greater Than | `bgt rs1 rs2 _label` | `if(rs1 > rs2) pc = &_label` | 0001_0000_0010 | 00_0000_0000 |
|  |  |  |  |  |  |  |
| sw | S | Save Word | `sw ma[offset] rs` | `(ma+offset) = rs` | 0010_0000_0000 | 00_0000_0000 |
|  |  |  |  |  |  |  |
| lw | L | Load Word | `lw rd ma[offset]` | `rd = *(ma+offset)` | 0011_0000_0000 | 00_0000_0000 |

