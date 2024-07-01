# task-4 "Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions 
ADD r1, r2, r3
SUB r3, r1, r2
AND r2, r1, r3
OR r8, r2, r5
XOR r8, r1, r4
SLT r10, r2, r4
ADDI r12, r3, 5
SW r3, r1, 4
SRL r16, r11, r2
BNE r0, r1, 20
BEQ r0, r0, 15
LW r13, r11, 2
SLL r15, r11, r2

Upload the 32-bit pattern on Github"
# An instruction set architecture (ISA)

An instruction set architecture (ISA) is a critical part of a computer's architecture that defines the commands a CPU can execute. 

It includes:
1. **Data Types**: Types of data the CPU can process (e.g., integers, floating point).
2. **Registers**: Small, fast storage locations within the CPU.
3. **Instruction Set**: The commands the CPU can execute (e.g., arithmetic operations, data movement).
4. **Instruction Formats**: The layout of bits in an instruction.
5. **Addressing Modes**: Methods for specifying operands (e.g., immediate, register, direct).
6. **Memory Architecture**: Organization and accessing methods for memory.
7. **Interrupt and Exception Handling**: Handling unexpected events or errors.
8. **External I/O**: Interaction with external devices.
Examples include x86, ARM, MIPS, PowerPC, and RISC-V.

# RISC-V ISA
A RISC-V ISA is made up of a base integer ISA that is necessary in every implementation and optional additions to it. The base integer ISAs are very similar to the original RISC (Reduced Instruction Set Computer) processors, with the difference of not having branch delay slots and not offering optional variable-length instruction encodings.
RISCV instructions are often written as 1 word = 4 bytes = 32 bits. Organize an instruction's 32 bits into "fields." X0-X31 general purpose registers are in addition to the hardwired constant 0 x0 register in the RV32I. Every register has a width of 32 bits, but in RV64I, they expand to 64 bits. A load-store architecture is RV32I. This indicates that arithmetic operations only employ the registers; only load and store instructions access memory. Space for users is 32 bit byte addressable and little endian .

we can define 6 instruction formats in RISC-V,

1. R-FORMAT
2. I-FORMAT
3. S-FORMAT
4. B-FORMAT
5. U-FORMAT
6. J-FORMAT

![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/1befc787-d96c-4622-9514-79aea1a502f2)

# 1.R-TYPE(Register) INSTRUCTIONS

* One of the instruction formats used in the risc-v isa is the r-type instruction format, which is used to execute arithmetic and logical instructions. The first field in the r-type instruction format is called the opcode field, which is also known as the operation code. 

* The  first field in the R - type instruction format is called  as opcode field which can also be called as operation  - code. This opcode is of 7-bit length (0 – 6) and this opcode is used to describe which type of instruction format is used such as R-type , I-type ,U-type etc.

* The next field in the R - type instruction format is called rd field. Rd here in the “rd field” stands for Destination Register. This rd field indicates the place where the result of the operation is stored .The length of the rd field is  5-bits (7-11).
funct3 (function - 3) is the field after the destination register .This field is 3 – bit length i.e. from bit 12 to bit 14 and it further tells about the operation, such as whether it is an addition, subtraction, or a logical operation that is being performed .                   

 * There are two source register namely rs1 and rs2 with the bit length of 5 bit each .rs1 is 5 bit length from 15 -19 and rs2 has bit length of 5 bit i.e. 20 -24.

* The funct7 field is the last field of R -type instruction format .It describes the operation, such as whether it is a shift or multiplication operation etc. Both funct3 and funct7 are used to describe the operations depending on the input format given to them.

  ![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/24d50e05-bd01-4f5c-9cee-b7595d445dfb)

  I-TYPE INSTRUCTION
  
* I stands for immediate in I-type instruction, indiactes the operations are executed using register and immediate values and are not depends on memory.
* The upper 12 bits of I-type is an immediate number.
* The opcode is different from other instruction formats because the corresponding specific operations are different, and other parts are very similar to R-type.

 ![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/1ddeaab2-f21d-418f-9525-b3130b2f07a6)


# S-TYPE INSTRUCTION 

* The characteristic of S-type instruction is that there is no rd register. In this type of instruction, the immediate is divided into two parts, the first part is in bit11-5, and the second part is in bit4-0. The 5 bits of the immediate 4-0 occupy the position of rd in other instruction formats, and 5-11 occupy the position of funct7.

* Explain that the command format does not need to write back. That is, read the two values from the two registers and perform the operation together with the immediate, and write the result to the register after the operation is over.

![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/15fb0d18-9f56-4a19-a231-9bda49d1ca9f)

# B-TYPE INSTRUCTION 

* B-type instructions are mainly used as branch instructions, but they are conditional Branch. It means to decide whether to jump or not need to depend on whether the condition is valid. The B-type machine code structure is shown in Figure 2-1.
* The instruction does not include rd register and funct7, but contains rs1, rs2, funct3 and immediate. The immediate is divided into two areas. The encoding of B-type instruction immediate is out of order. The reason is not described in detail here.
* It has been verified that the effect on CPU operation function when the immediate number sequence is in this order is very well. But the immediate is disrupted, so it will be decoded when the CPU executes in the future. After decoding, the CPU needs to restore the disrupted immediate in order. For example, when the CPU gets a B-type instruction, the immediate in it is scrambled, and the CPU needs to arrange the immediate in the order of 12-1 to restore the immediate.

![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/5a9bdf3c-0397-4850-b839-11a7e9f16fe5)

# U-TYPE INSTRUCTION 

* A 20-bit immediate is provided in the U-type instruction.
* The final operation result is related to the 20-bit immediate, and the result is written back to the rd register.
* The opcode determines the type of operation. There are no funct3, rs1, rs2, and funct7 in U-type.
* This type of instruction structure is very simple.

![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/9326cf90-4799-471b-8a17-bce16f3cf1c2)

# J-TYPE INSTRUCTION

* The format of this instruction is very similar to U-type, it only have Rd register and immediate and opcode. 
* At the same time, the immediate of J-type is also disrupted. That means that the CPU must first put the immediate numbers together to restore the original immediate numbers when decoding.

![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/c9318988-1d8b-49b7-b00c-06f931319766)


![image](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/cc9849d8-4b50-420b-a865-cd1998f6c050)


  # NOW LET US DECODE THE INSTRUCTIONS GIVEN TO US

 1. ADD r1, r2, r3

* Instruction:ADD
* Type: R-Tpye
* Format:opcode[6:0]|rd[11:7]|funct3[14:120]|rs[19:16}|rs2[24:20]|funct[31:25]
* Encoding:

  - opcode = 0110011 (0x33)
  - rd = r6 (0b00110)
  - funct3 = 000
  - rs1 = r2 (0b00010)
  - rs2 = r1 (0b00001)
  - funct7 = 0000000

#### - *32-bit Code*: 0000000 00011 00001 111 01000 0110011

- *Hex*: 0x0030C033

#### 4. *OR r9, r2, r5*

- *Instruction*: OR

- *Type*: R-Type

- *Format*: Same as above.

 *Encoding*:

              - opcode = 0110011 (0x33)
              - rd = r6 (0b00110)
              - funct3 = 000
              - rs1 = r2 (0b00010)
              - rs2 = r1 (0b00001)
              - funct7 = 0000000

#### - *32-bit Code*: 0000000 00101 00010 110 01001 0110011

- *Hex*: 0x0052C033

#### 5. *XOR r10, r1, r4*

- *Instruction*: XOR

- *Type*: R-Type

- *Format*: Same as above.

- *Encoding*:

              - opcode = 0110011 (0x33)
              - rd = r10 (0b01010)
              - funct3 = 100
              - rs1 = r1 (0b00001)
              - rs2 = r4 (0b00100)
              - funct7 = 0000000

#### - *32-bit Code*: 0000000 00100 00001 100 01010 0110011

- *Hex*: 0x0040A033

#### 6. *SLT r11, r2, r4*

- *Instruction*: SLT (Set Less Than)

- *Type*: R-Type

- *Format*: Same as above.

- *Encoding*:

              - opcode = 0110011 (0x33)
              - rd = r11 (0b01011)
              - funct3 = 010
              - rs1 = r2 (0b00010)
              - rs2 = r4 (0b00100)
              - funct7 = 0000000

#### - *32-bit Code*: 0000000 00100 00010 010 01011 0110011

- *Hex*: 0x00415033

#### 7. *ADDI r12, r4, 5*

- *Instruction*: ADDI (Add Immediate)

- *Type*: I-Type

- *Format*: opcode[6:0] | rd[11:7] | funct3[14:12] | rs1[19:15] | imm[31:20]

- *Encoding*:

              - opcode = 0010011 (0x13)
              - rd = r12 (0b01100)
              - funct3 = 000
              - rs1 = r4 (0b00100)
              - imm = 5 (0b000000000101)

#### - *32-bit Code*: 000000000101 00100 000 01100 0010011

- *Hex*: 0x00520113

#### 8. *SW r3, r1, 2*

- *Instruction*: SW (Store Word)

- *Type*: S-Type

- *Format*: opcode[6:0] | imm[11:7] | rs2[24:20] | rs1[19:15] | funct3[14:12] | imm[4:0]

- *Encoding*:

              - opcode = 0100011 (0x23)
              - imm[11:5] = 0 (upper part of 2 is 0)
              - rs2 = r3 (0b00011)
              - rs1 = r1 (0b00001)
              - funct3 = 010
              - imm[4:0] = 2 (0b00010)

#### - *32-bit Code*: 0000000 00011 00001 010 00010 0100011

- *Hex*: 0x00312223

#### 9. *SRL r16, r14, r2*

- *Instruction*: SRL (Shift Right Logical)

- *Type*: R-Type

- *Format*: Same as above.

- *Encoding*:

              - opcode = 0110011 (0x33)
              - rd = r16 (0b10000)
              - funct3 = 101
              - rs1 = r14 (0b01110)
              - rs2 = r2 (0b00010)
              - funct7 = 0000000

#### - *32-bit Code*: 0000000 00010 01110 101 10000 0110011

- *Hex*: 0x00273333

#### 10. *BNE r0, r1, 20*

- *Instruction*: BNE (Branch Not Equal)

- *Type*: B-Type

- *Format*: opcode[6:0] | imm[11] | imm[4:1] | funct3[14:12] | rs1[19:15] | rs2[24:20] | imm[10:5] | imm[12]

- *Encoding*:

              - opcode = 1100011 (0x63)
              - imm = 20 (0b0000000001010)
              - rs1 = r0 (0b00000)
              - rs2 = r1 (0b00001)
              - funct3 = 001

#### - *32-bit Code*: 0000000 00101 00001 001 00000 1100011

- *Hex*: 0x01408063

#### 11. *BEQ r0, r0, 15*

- *Instruction*: BEQ (Branch Equal)

- *Type*: B-Type

- *Format*: Same as above.

- *Encoding*:

              - opcode = 1100011 (0x63)
              - imm = 15 (0b0000000000111)
              - rs1 = r0 (0b00000)
              - rs2 = r0 (0b00000)
              - funct3 = 000

#### - *32-bit Code*: `0000000 000



  

