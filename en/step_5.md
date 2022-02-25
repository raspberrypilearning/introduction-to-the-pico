## Potentiometers

A potentiometer is a resistor that allows you to change the value of the resistance. They are often just called **pots**.

![a side by side photograph of a potentiometer, showing the three pins and the arrow on the dial](images/potentiometer.jpg)

A potentiometer has three pins. The outer pins are normally connected to a 3V3 pin and a GND pin. The middle pin is connected to a GPIO pin capable of reading an analogue signal

![diagram of a potentiometer with the left pin labeled GND and the right pin labeled 3V3](images/potentiometer-illustration.png)

Turning the dial on the top of the potentiometer will change the resistance of the potentiometer, which can then be read by the Raspberry Pi Pico.

You can wire up a potentiometer to a Raspberry Pi Pico as shown below.

![A potentiometer wired to a Raspberry Pi Pico, with the signal pin wired to GP26](images/pot-diagram.png)

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