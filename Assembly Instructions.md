See [[Assembly Structure]] for structure of instructions

### Key
* `rsx, rd` refer to register source 1 or 2 and register destination
* `imm` refers to the immediate value
* `&, *` & refers to the value cast as an address, and * refers to the value at the address

## Notes
* Any ALU output can be notted by setting the 4th bit of the funct code to `1`
	* This has no effect on instructions that do not use the ALU
	* In asm, add a `_n` at the end of the instruction to signal the notting of the output (ie `add_n rd rs1 rs2`)



| Instruction | Type | Description | Syntax | Function | opcode |
| ---- | ---- | ---- | ---- | ---- | ---- |
| add | R | Add | `add rd rs1 rs2` | `rd = rs1 + rs2` | 0000_0000_0000 |
| sub | R | Subtract | `sub rd rs1 rs2` | `rd = rs1 - rs2` | 0000_0000_0001 |
| mul | R | Multiply | `mul rd rs1 rs2` | `rd = rs1 * rs2` | 0000_0000_0010 |
| and | R | and | `and rd rs1 rs2` | `rd = rs1 \| rs2` | 0000_0000_0011 |
| or | R | or | `or rd rs1 rs2` | `rd = rs1 ^ rs2` | 0000_0000_0100 |
| xor | R | xor | `xor rd rs1 rs2` | `rd = rs1 & rs2` | 0000_0000_0101 |
| slt | R | set less than | `slt rd rs1 rs2` | `rd = rs1 < rs2` | 0000_0000_0110 |
| sgt | R | set greater than | `sgt rd rs1 rs2` | `rd = rs1 > rs2` | 0000_0000_0111 |
| seq | R | set equals | `seq rd rs1 rs2` | `rd = rs1 == rs2` | 0000_0000_1000 |
| addc | R | add carry | `addc rd rs1 rs2` | `rd = rs1 + rs2 (carry)` | 0000_0000_1001 |
| mulc | R | multiply carry | `mulc rd rs1 rs2` | `rd = rs1 * rs2 (carry)` | 0000_0000_1010 |
| lshift | R | left shift | `lshift rd rs1 rs2` | `rd = rs1 << rs2` | 0000_0000_1011 |
| rshift | R | right shift | `rshift rd rs1 rs2` | `rd = rs1 >> rs2` | 0000_0000_1100 |
| RESERVED | R |  |  |  | 0000_0000_1101 |
| RESERVED | R |  |  |  | 0000_0000_1110 |
| RESERVED | R |  |  |  | 0000_0000_1111 |
| addi | I | Add Immediate | `addi ds rs1 imm` | `rd = rs1 + imm` | 0001_0000_0000 |
| subi | I | Subtract Immediate | `subi rd rs1 imm` | `rd = rs1 - imm` | 0001_0000_0001 |
| muli | I | Multiply Immediate | `muli rd rs1 imm` | `rd = rs1 * imm` | 0001_0000_0010 |
| andi | I | and | `andi rd rs1 imm` | `rd = rs1 & imm` | 0001_0000_0011 |
| ori | I | or | `ori rd rs1 imm` | `rd = rs1 \| imm` | 0001_0000_0100 |
| xori | I | xor | `xori rd rs1 imm` | `rd = rs1 ^ imm` | 0001_0000_0101 |
| slti | I | set less than | `slti rd rs1 imm` | `rd = rs1 < imm` | 0001_0000_0110 |
| sgti | I | set greater than | `sgti rd rs1 imm` | `rd = rs1 > imm` | 0001_0000_0111 |
| seqi | I | set equals | `seqi rd rs1 imm` | `rd = rs1 == imm` | 0001_0000_1000 |
| addci | I | add carry | `addci rd rs1 imm` | `rd = rs1 + imm (carry)` | 0001_0000_1001 |
| mulci | I | multiply carry | `mulci rd rs1 imm` | `rd = rs1 * imm (carry)` | 0001_0000_1010 |
| lshifti | I | left shift | `lshifti rd rs1 imm` | `rd = rs1 << imm` | 0001_0000_1011 |
| rshifti | I | right shift | `rshifti rd rs1 imm` | `rd = rs1 >> imm` | 0001_0000_1100 |
| RESERVED | I |  |  |  | 0001_0000_1101 |
| RESERVED | I |  |  |  | 0001_0000_1110 |
| RESERVED | I |  |  |  | 0001_0000_1111 |
| jtl | I | Jump to Label | `jtl _label` | `pc = &_label` | 0001_0010_0000 |
| beq | I | Branch if Equal | `beq rs1 rs2 _label` | `if(rs1 == rs2) pc = &label` | 0001_0010_0001 |
| blt | I | Branch if Less Than | `blt rs1 rs2 _label` | `if(rs1 < rs2) pc = &label` | 0001_0010_0010 |
| bgt | I | Branch if Greater Than | `bgt rs1 rs2 _label` | `if(rs1 > rs2) pc = &label` | 0001_0010_0011 |
| sw | S | Save Word | `sw ma[offset] rs1` | `(ma+offset) = rs1` | 0010_0000_0000 |
| simem | S | Save to Instruction Mem | `simem ma[offset] rs1` | `(ma+offset) = rs1` | 0010_0000_0001 |
| lw | L | Load Word | `lw rd ma[offset]` | `rd = *(ma+offset)` | 0011_0000_0000 |

 