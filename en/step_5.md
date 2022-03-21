## Install the picozero library

`picozero` is a MicroPython library for beginners to the Raspberry Pi Pico. 

--- task ---

To complete the projects in this path, you will need to install the picozero library as a Thonny plug-in.

In Thonny, choose 'Tools > Manage plugins...'.

![The Thonny Tools menu with Manage plugins highlighted.](images/thonny-manage-plugins.png)

In the pop-up 'Thonny plug-ins' window, type `picozero` and click 'Search on PyPi'.

![Thonny plugins search results showing picozero.](images/thonny-plugins-picozero.png)

Click on 'picozero' in the search results. 

Click on 'Install'.

![The picozero information with 'Install' button highlighted.](images/path.png)

When installation has completed, close the plug-in window then exit and reopen Thonny.

<mark>Check install process works.</mark>

--- /task ---

To check that the library is installed correctly, you can write a program to light the LED on the Raspberry Pi Pico.

--- task ---

Look at your Raspberry Pi Pico and find the small LED next to the USB connector. 

![A photo of the Raspberry Pi Pico with the LED highlighted](images/pico-led.jpg){:width="200px"}

--- /task ---

--- task ---

Create a new file in Thonny by clicking 'File > New' in the top menu bar. An empty workspace should open.

--- /task ---

--- /task ---

--- task ---
The simplest program you can write with `picozero` is:

--- code ---
---
language: python
filename: main.py
line_numbers: false
line_number_start: 
line_highlights: 
---

from picozero import pico_led

pico_led.on()

--- /code ---


--- /task ---