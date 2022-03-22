## Potentiometers

A potentiometer is a resistor that allows you to change the value of the resistance. They are often just called **pots**.

![a side by side photograph of a potentiometer, showing the three pins and the arrow on the dial](images/potentiometer.jpg)

A potentiometer has three pins. The outer pins are normally connected to a 3V3 pin and a GND pin. The middle pin is connected to a GPIO pin capable of reading an analogue signal

![diagram of a potentiometer with the left pin labeled GND and the right pin labeled 3V3](images/potentiometer-illustration.png)

Turning the dial on the top of the potentiometer will change the resistance of the potentiometer, which can then be read by the Raspberry Pi Pico.

[[[potentiometer-wiring]]] 

The potentiometer 

[[[potentiometer-pin]]]

The following code will read a value from the potentiometer and print out the result.

--- code ---
---
language: python
filename: main.py
line_numbers: false
line_number_start: 
line_highlights: 
---
from picozero import Pot
from time import sleep

dial = Pot(0) # Connected to pin A0 (GP_26)

while True:
    print(dial.value)
    sleep(0.1)
--- /code ---

--- collapse ---

title: Call a function based on the value of the potentiometer
If you are using a potentiometer to control outputs then you will need to divide up the dial into equal sections.

You can use dial.percent to get a value between 0 and 1 from the potentiometer. If you have 5 moods then you can check whether the value is less than 20, 40, 60, 80 or 100. If you have 3 moods then you can check whether the value is less that 33, 66 or 100.

--- code ---
language: python filename: sensory-gadget.py line_numbers: false line_number_start: line_highlights:
while True: mood = dial.percent print(mood) if mood < 20: happy() elif mood < 40: good() elif mood < 60: okay() elif mood < 80: unsure() else: unhappy() sleep(0.1)

--- /code ---

--- /collapse ---