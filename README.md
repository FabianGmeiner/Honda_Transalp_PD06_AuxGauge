# Honda_Transalp_PD06_AuxGauge
Auxiliary Gauge for a Honda XL600V Transalp PD06

# About this project
I wanted to make a little digital clock for my Transalp since I use it for commuting a lot. Then I thought, while I'm at it I might as well add an oil temperature gauge and a voltmeter function. I 3D-Scanned the original fusebox cover, designed a slightly taller cover to allow the gauge pcb and display to sit above the fuses and created the gauge itself in KiCad. The gauge uses an Arduino Nano as its brain, a black EA DOGM 162 LCD with white (or whatever color you want) backlight and a DS3231 RTC chip. The temp gauge can be set up to work with common 1k NTC sensors (e.g. VDO, MotoMeter) or 2.2K sensors as found in Alfa Romeo vehicles which have a fitting M14x1.5 thread size to replace the oil drain plug. 

# How to operate the gauge - what does the button do?
The gauge boots up in the normal display state. The button has three function, a single click, a double-click or a long press. in the normal display state, a single or double-click will toggle the display brightness between bright and dim, while a long press will enter the menu. While in the menu, a single click increments the value, a double-click decrements the value and a long press will move to the next menu entry. To get back to the display state, cycle through all of the menu entries until you return to the display state. In the menu, you can set the brightness for the bright and dim setting, set the time, define warning thresholds for temperature and voltage and select the NTC sensor type.

# How to build it yourself
If you want to build this gauge yourself, you can use the files in the production-folder [https://github.com/FabianGmeiner/BMW_E30_SI_Board/blob/main/BOM_SI_Board_Reman.xlsx "BOM_SI_Board_Reman.xlsx"](https://github.com/FabianGmeiner/Honda_Transalp_PD06_AuxGauge/tree/main/Production) to order the populated pcb and the 3D-printed housing at the fabhouse of your choice. I ordered everything at JLCPCB, thats what the BOM and CPL files are formatted for. The housing is 3D-printed at JLC3DP as well from their 3201PA-F Nylon making it very robust and temperature resistant considering its going to be exposed to direct sunlight. In addition, you'll need the parts described in the [BOM](https://github.com/FabianGmeiner/Honda_Transalp_PD06_AuxGauge/blob/main/BOM_Transalp_PD06_AuxGauge.xlsx), as well as some fitting connectors to wire everything in. 

I got the fitting OEM connectors from Classic Bike Parts in germany ([Male](https://www.classic-bike-parts.de/CBP-Vielfachstecker-JP63-2-polig-mit-Flachstecker-63-multiple-plug-with-flat-plug), [Female](https://www.classic-bike-parts.de/CBP-Vielfachstecker-JP63-2-polig-mit-Steckhuelsen-63-multiple-plugs-with-receptacles)) but any supplier works. For the 3-Pin connector I used [this one](https://www.classic-bike-parts.de/CBP-Vielfachstecker-JP28-3-polig-mit-Flachstecker-28mm-multiple-plug-with-flat-plug). 

If you plan on using the white, green/yellow or blue backlight, the populated current limiting resistors will work fine. If you plan on using the amber or red backlight, you should increase the resistor values of R11 and R12 to 36 or 39Ohm, or at least make sure not to set the brightness to 100%.  

# How to asseble the PCB
First, the arduino needs to be soldered onto the backside. As space is a bit limited, I trimmed off the pin headers flush with the PCB before soldering the pins, so the solder joints only slighly protrude through to the top side of the PCB. I then place a layer of insulating tape over the solder joints before placing and soldering the LCD screen with its backlight. Note that the four front LCD pins have to also be soldered to the LED backlight, not just to the main PCB. Afterwards you can solder the coin cell holder, two wires for the button and the power supply and temp sensor wire. Make sure to get the polarity of the power supply correct, as the input is ESD and overvoltage protected, but not reverse polarity protected. 

# How to connect it to the bike
Power supply and voltage takeoff is done by building a little extension cable that plugs in between the cooling fan connectors underneith the tank (1A inline fuse recommended). At the gauge itself i soldered a 30cm pigtail harness terminated in a 3-pin connector, just so it can be taken off the bike without having to pull all the wiring out. For the NTC sensor, a single wire with a 6.3mm spade connector needs to be routed down to the sensor. 


