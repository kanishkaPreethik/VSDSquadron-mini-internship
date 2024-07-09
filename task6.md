# Overview, Components Required to build your application, Circuit Connection, Pinout Diagram using ppt (current image is hand-drawn) and Table for Pin connection. 

# Developing a 7Segment Display using VSDSsquadron Mini.

## OVERVIEW 

The project showcases a creative way to integrate the RISC-V CH32V003 processor to make a 7 section LED display driver. The processor converts the given number into its binary equivalent and signals each segment whether or not to glow based on the bits it receives. Therefore, we can automate the display rather than having to set it manually every time. We are only currently driving one display, future work will involve combining two displays.

## COMPONENTS REQUIRED 
1. VSDSquadron Mini
2. Breadboard
3. seven segment display
4. resistors
5. jumper wires
6. power supply

# CIRCUIT CONNECTION 

Connect the Common Anode/Cathode pin to VCC or GND via a resistor depending on the type of display.
Connect PD0 to pin a of the display.
Connect PD1 to pin b of the display.
Connect PD2 to pin c of the display.
Connect PD3 to pin d of the display.
Connect PD4 to pin e of the display.
Connect PD5 to pin f of the display.
Connect PD6 to pin g of the display.

# PIN DIAGRAM FOR THE PROJECT

Pin diagram for common cathode seven segment led:

![IMG20240709230206](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/df64f6a8-7551-46ef-8d47-c5c275a5aaec)

# TABLE FOR PIN CONNECTION 

| 	SEVEN SEGEMENT	 | 	RISC-V |
| 	:-----:	 | 	:-----:	 | 
| 	a	| 	PD0	|
| 	b	|   PD1 |
| 	c	| 	PD2	|
| 	d	| 	PD3	|
| 	e	| 	PD4	|
| 	f	| 	PD5	|
| 	g	| 	PD6	|
| 	CA/CC	| 	VCC/GND	|

# Task 6 completed 
