# write a simple c program for your project selected and compiled with RISC-v GCC

# my project is to develop  7 segment display driver.

# An overview of 7 Segment Display.

# A 7-segment display is an electronic display device used to display digits and some alphabetic characters. It consists of seven LED segments arranged in a rectangular fashion, with each segment labeled from 'a' to 'g'. By illuminating specific segments in combination, it can represent numbers 0-9 and some letters. It's commonly used in digital clocks, calculators, and other electronic devices requiring numerical display.

![Screenshot 2024-06-25 190310](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/b6871dea-aa99-42ac-95bb-ff4afb16eeda)

# Types of 7 segment 
# There are primarily two types of 7-segment displays: Common Anode (CA) and Common Cathode (CC). Here's an explanation of each type:

# 1. Common Anode (CA)
# Configuration: In a common anode 7-segment display, all the anodes of the LEDs are connected together to a common terminal, usually connected to a positive voltage (Vcc).
# Operation: To illuminate a particular segment, the corresponding cathode pin is connected to ground (0V). The common anode must be connected to a positive voltage, and the segments are turned on by grounding their respective pins.
# Application: This type is often used in digital clocks, calculators, and other devices where a consistent high voltage supply is available.

# 2. Common Cathode (CC)
# Configuration: In a common cathode 7-segment display, all the cathodes of the LEDs are connected together to a common terminal, which is usually connected to ground (GND).
# Operation: To illuminate a particular segment, the corresponding anode pin is connected to a positive voltage (Vcc). The common cathode must be connected to ground, and the segments are turned on by applying a high voltage to their respective pins.
# Application: This type is commonly used in battery-powered devices and other applications where grounding individual segments is more convenient.

![images](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/97357cbe-a8fb-432e-b45e-e699569678df)

![7-Segment-Display-Types](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/323364b4-381a-49de-85aa-63cc45adeb63)

# The truth-table shown in the below image shows the state of the outputs for various inputs. Since, we are making driver for common anode  display, '0' represents that the corresponding LED is on and vice-versa.

# ![ec747c67-06a4-414c-a86d-109c9aa5582e](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/3bca360a-7a9f-4d37-92e8-d10e417033be)

# The coding  part 

![Screenshot from 2024-06-25 19-18-21](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/f6ae3f18-4d4c-4fd5-aa4d-650d79bbac73)
![Screenshot from 2024-06-25 19-18-49](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/8b602135-ed90-44b6-b37b-ce2d4d589139)
![Screenshot from 2024-06-25 19-23-03](https://github.com/kanishka-preethi/VSDSquadron-mini-internship/assets/173462509/3088cc20-9cc7-4657-9cd5-f64cc0c1aaeb)

