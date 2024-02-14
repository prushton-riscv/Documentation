## Abstract

This processor is a fork of the risc-v processor architecture. After reviewing the MIPS processor and some other RISC-V architectures, I decided that there were features that I liked and didnt like. One of the main dislikes was the lack of ALU functionality, which you can see is massively increased as opposed to MIPS. Another goal I has was to have 2 cores, where one main core could send instructions to a secondary core for parallel execution.

## Architecture
This is the entire architecture of the processor. View [[RISC-V.excalidraw]] for a higher definition image
![[RISC-V.excalidraw]]

Note all blue signals are sent to the second core, which is functionally the same as the primary core.

Here are some of the key differences that I did to allow for more efficient assembly:
* Jump address can be called from a register, processed in the ALU, and wroteback in the same cycle
* ALU can be sourced from the immediate and the program counter, and these are on source b and a respectively
* Instructions are indexed by 1 not 4 preventing issues where a non 4 divisible int can be added and two instructions can be loaded at once
* Data memory has 2 writes and 3 reads to allow for both processors and a video output from the same module


## ALU
view [[ALU.excalidraw]] 
![[ALU.excalidraw]] 

After reviewing the MIPS ALU, I came up with this
* Both A and B can be notted, allowing for either to be negative
* More operations including left shift, multiply, carry, etc
* Notting of the output to make all 6 gates accessible in one cycle