## LEDs

Light Emitting Diodes (LEDs) produce light when a current is passed through them, from the long leg (the anode) to the short leg (the cathode).

<a title="PiccoloNamek, CC BY-SA 3.0 &lt;http://creativecommons.org/licenses/by-sa/3.0/&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:RBG-LED.jpg"><img width="512" alt="RBG-LED" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/RBG-LED.jpg/512px-RBG-LED.jpg"></a>

An LED will often need a resistor to be used in series with it. This is because too much current can cause an LED to burn out, or even explode.

To get the maximum brightness from an LED, you need to find the correct resistor.

When you buy an LED, you can normally look at a datasheet for it, and find it's `forward voltage` and `forward current`.

| Parameter | Value |
|-----------|-------|
|**Forward voltage drop**|**2.1V**|
|Viewing angle|25 degrees
|**Max forward current**|**25 mA**|
|Luminous intensity|600 -1000 mCd (@20mA)|
|Lens types|Water Clear|

You also need to know your supply voltage, which for Raspberry Pi Pico will be 3.3V.

To know which resistor you need, you can use this calculation.

<math xmlns="&mathml;">
<mrow>
<mi>Needed Resistance</mi>
<mo>=</mo>
</mrow>
<mfrac>
<mrow>
  <mi>Supply Voltage</mi>
  <mo>-</mo>
  <mi>Forward Voltage of LED</mi>
</mrow>
  <mi>Forward Current of LED (in Amps, so divide by 1000)</mi>
</mfrac>
</math>
<br>
For instance, for the LED data above needs a resistor of at least 48Ω
<br>
<math xmlns="&mathml;">
<mrow>
<mi>Needed Resistance</mi>
<mo>=</mo>
</mrow>
<mfrac>
<mrow>
  <mi>3.3</mi>
  <mo>-</mo>
  <mi>2.1</mi>
</mrow>
  <mi>0.025</mi>
</mfrac>
</math>
<br>

Your resistor can be connected to either leg of your LED, and then to your Raspberry Pi Pico.

[[[led-resistor-electrical-tape]]]

[[[led-resistor-solder-heat-shrink]]]

![Raspberry Pi Pico connected to an LED and resistor](images/pico_led_13_bb.png)


To turn your LED on and then off again, you could use the following code.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 
line_highlights: 
---
from picozero import LED
from time import sleep

yellow = LED(13)
yellow.on()
sleep(2)
yellow.off()
--- /code ---