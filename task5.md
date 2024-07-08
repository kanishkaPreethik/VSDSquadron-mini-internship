# Using RISC-V Core Verilog netlist and testbench for functional simulation experiment.In this we need to find the output waveforms for the instructions which we learnt in Task 4.
Follow the steps to obtain the waveform for the instructions used in Task 4.
The Verilog Code and Testbench used is refered by https://github.com/vinayrayapati/rv32i/

1. first we need to give the command:
                            sudo apt-get update
                            sudo apt-get install iverilog gtkwave
   
3. now we need to setup our project directory for your project and place your verilog files and test bench there.
                   mkdir kanishka 
                   cd kanishka
   
3.Copy the code from the reference code and paste it in a file name under kanishka_rv32i.v and kanishka_rv32i_tb.v

4.Give command line as touch kanishka_rv32i.v and touch kanishka_rv32i_tb.v in leafpad.

5.Run and simulate the verilog code by using the below command;
                                 iverilog -o kanishka_rv32i kanishka_rv32i.v kanishka_rv32i_tb.v
                                ./kanishka_rv32i
6.View the Waveform Open the waveform file using GTKWave:
                                 gtkwave iiitb_rv32i.vcd
                                 
7.7.Then GTKWave will open

![Screenshot 2024-07-08 203455](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/0498e88c-0b91-4979-ba7c-a873717d4d9c)

![Screenshot 2024-07-08 205104](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/d51aa2c0-ed61-4e8b-a57c-5799b2954f05)

![Screenshot 2024-07-08 205307](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/01792217-ce7b-4cc3-b715-29be8260b59c)

8.Now, drag the command in the same way presented under time section.

Select the instructions from EX_MEM_IR[31:0] to present the instructions used in Task 4.

Instruction ADD r1, r2, r3 :

![Screenshot 2024-07-08 205333](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/6fbedee8-c819-4a8f-9d7e-f6964493b0c5)

Instruction SUB r3, r1, r2 :

![Screenshot 2024-07-08 205405](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/3936bb2e-a84f-4769-ae90-9a0d0870c351)

Instruction AND r2, r1, r3 :

![Screenshot 2024-07-08 205433](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/dc974442-9403-41c4-b574-acf7f47954bc)

Instruction OR r8, r2, r5 :

![Screenshot 2024-07-08 205506](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/c65105dd-2201-46b2-adcf-48cb3d1e147a)

Instruction XOR r8, r1, r4 :

![Screenshot 2024-07-08 205611](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/7c3ea461-2300-49ac-b38b-26eab8429e5e)

Instruction SLT r10, r2, r4 :

![Screenshot 2024-07-08 205654](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/6495b664-aa95-4680-b247-d71bc927195f)

Instruction ADDI r12, r3, 5 :

![Screenshot 2024-07-08 205720](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/645b2f32-bb8a-43d7-8396-8b3793a1f431)

Instruction SW r3, r1, 4 :

![Screenshot 2024-07-08 205757](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/30e7abfa-6b76-4fa9-8c1c-aaac3c245c79)

Instruction SRL r16, r11, r2 :

![Screenshot 2024-07-08 205757](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/8f325fea-37c9-4c47-a151-37307bf77fa6)

Instruction BNE r0, r1, 20 :

![Screenshot 2024-07-08 205757](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/62f1c2e6-f614-4fb2-8892-17680ea5a407)

Instruction SLL r15, r11, r2 :

![Screenshot 2024-07-08 205827](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/a1d32f69-0bae-4cf1-a15e-129404b56be2)

# task-5 completed 

