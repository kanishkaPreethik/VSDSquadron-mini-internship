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

![Screenshot 2024-07-23 122933](https://github.com/user-attachments/assets/7646379d-79fa-4661-a9f4-6691544ef7b3)

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

# Code uploaded on board 

// #include <stdio.h>
#include <ch32v00x.h>
#include <debug.h>

// Define the GPIO pins for the driver

#define a GPIO_Pin_0        // Pin for segment a
#define b GPIO_Pin_0        // Pin for segment b
#define c GPIO_Pin_2        // Pin for segment c
#define d GPIO_Pin_3        // Pin for segment d      
#define e GPIO_Pin_4        // Pin for segment e    
#define f GPIO_Pin_5        // Pin for segment f    
#define g GPIO_Pin_6        // Pin for segment g    

int outar[] = {0,0,0,0,0,0,0};
int out[] = {126 , 48, 109, 121, 51, 91, 95, 112, 127, 123, 119, 31, 78, 61, 79, 71};

// Function prototypes
void GPIO_Config(void);
void assign(int);

// GPIO configuration function
void GPIO_Config(void) {
    GPIO_InitTypeDef GPIO_InitStructure = {0};


    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // Enable clock for Port D
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE); // Enable clock for Port C

    // Configure pin a as output

    GPIO_InitStructure.GPIO_Pin = a;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin b as output

    GPIO_InitStructure.GPIO_Pin = b;
    GPIO_Init(GPIOC, &GPIO_InitStructure);

    // Configure pin c as output

    GPIO_InitStructure.GPIO_Pin = c;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin d as output

    GPIO_InitStructure.GPIO_Pin = d;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin e as output

    GPIO_InitStructure.GPIO_Pin = e;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin f as output

    GPIO_InitStructure.GPIO_Pin = f;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Configure pin g as output

    GPIO_InitStructure.GPIO_Pin = g;
    GPIO_Init(GPIOD, &GPIO_InitStructure);
}

int main()
{
   // SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();
  while(1)
  {
    for(int i = 0; i < 16; i++)
    {
        assign(i);
        if(outar[6]==1)
        GPIO_WriteBit(GPIOD, a, SET);
        else
        GPIO_WriteBit(GPIOD, a, RESET);

        if(outar[5]==1)
        GPIO_WriteBit(GPIOC, b, SET);
        else
        GPIO_WriteBit(GPIOC, b, RESET);
       
        if(outar[4]==1)
        GPIO_WriteBit(GPIOD, c, SET);
        else
        GPIO_WriteBit(GPIOD, c, RESET);
       
        if(outar[3]==1)
        GPIO_WriteBit(GPIOD, d, SET);
        else
        GPIO_WriteBit(GPIOD, d, RESET);
       
        if(outar[2]==1)
        GPIO_WriteBit(GPIOD, e, SET);
        else
        GPIO_WriteBit(GPIOD, e, RESET);
       
        if(outar[1]==1)
        GPIO_WriteBit(GPIOD, f, SET);
        else
        GPIO_WriteBit(GPIOD, f, RESET);
       
       
        if(outar[0]==1)
        GPIO_WriteBit(GPIOD, g, SET);
        else
        GPIO_WriteBit(GPIOD, g, RESET);
        Delay_Ms(5000);
    }
    return 0;
  }
}

void assign(int num)
{
    int mask = 1;
    for( int i = 0; i<7; i++)
    {
        if((mask & out[num]) == 0)
            outar[i] = 0;
        else
            outar[i] = 1;
        mask = mask<<1;
    }
}


# Task 6 completed 
