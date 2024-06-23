# TASK 1

## Writing a C code to count the sum of numbers from 1 to n and running this program using RISC-V simulator

## Writing a C code to count sum of numbers from 1 to n

![Screenshot 2024-06-23 143130](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/9c0d5bb0-2c46-446a-833f-8fe96ad2d085)

#### 1. First I opened terinal and wrote code to make and open a new C file in leafpad as shown below:

![Screenshot 2024-06-23 143222](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/32aefeec-27ec-4040-95b2-ebb6535ea8eb)

#### 2. Then I wrote my code in leafpad as shown below:

![Screenshot 2024-06-23 143315](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/20550332-6165-422e-96b6-2d00e65171a6)

#### 3. And then compiled and run in terminal itself to check, and got the desired output.

![Screenshot 2024-06-23 143341](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/d6ee3dc4-9c3d-49f0-9eed-4706598a1d88)

#### 4. Tried for different value of n and got the results, like n=100.

![Screenshot 2024-06-23 143408](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/5c64aa29-5f8e-44aa-9198-28880097a091)

![Screenshot 2024-06-23 143435](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/583b1725-365c-4297-87d8-0e28ff88ed48)

## Running above program in RISC-V Simulator

#### Once I have ran the code in terminal, I need to run in RISC-V simulator so for that their is special set of code needed which I have done in following steps:

#### 1. First I wrote a code to compile it with RISC-V gcc compiler with option 1 so it will generate a file with .o extension.

![Screenshot 2024-06-23 143503](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/01f21836-2368-4ebd-afd3-f458e222ae3e)

#### 2. Next I wrote a code riscv-unknown-elf-objdump -d sum1ton.o for getting the assembly code for the above c program, and got many assembly codes. Reduced the number of assembly codes just by writing | less after the command. We wanted main section so I searched for the main. The byte address for main was found to be 10184 and got 15 instrusctions when using option 1. It is observed that the address of each consecutive instructions get incremented by 4.

![Screenshot 2024-06-23 143523](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/684418bb-a9f9-4ca3-bf0c-0048c817640b)

![Screenshot 2024-06-23 143631](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/dcf72d75-312f-41db-b74a-a2bdce76f1c8)

![Screenshot 2024-06-23 143653](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/d460f0dd-51ae-472a-b3f5-7f4060c7067e)

#### 3. Next I run the same commands but with different option, instead of O1, I used Ofast. This time I got less number of instructions i.e. 12. This shows that the instrunctions in assembly codes of the file changes for different options of compilation.

![Screenshot 2024-06-23 143711](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/e97c42bf-5820-4e34-9480-e905a8bc2b0e)

## That is it for Task 1
