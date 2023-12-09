# Meterized LED Magic

Spread the light ☀️
![Beschreibung des Bildes](images/strips_total.gif)

## Overview
This is our meterized LED bar system. It is designed to be cheap, simple and modular

![Beschreibung des Bildes](images/strips_total.jpeg)
![Beschreibung des Bildes](images/strips_ceiling.jpeg)

## LED Bars

![Beschreibung des Bildes](images/LED_bar.jpeg)

Simplicity is key. Each bar has 5 components. A aluminum bar, a diffuser, 3D printed end pieces, an LED strip and a short DMX cable on each side. This makes them relatively simple to build and maintain,controller independent and modular. Bars can be connected in line with standard DMX cables for maximal flexibility.
Line length is limited by voltage drop and diminishing signal integrity over distance. 12 Strips in a line is a good limit for our setup. Results vary based on cable length.
Each 1m LED Bar has 60 pixels - 




## Power & Controls
![Beschreibung des Bildes](images/controller_power.jpeg)    
### Power
We use a 12V 380W power supplies, as they allow us to max out our controllers generation/translation capabilities for the connected pixels. Read more [here](https://kno.wled.ge/features/multi-strip/). 
For the set-up in the pictures above we use one power supply and controller each to control 4 lines of LED bars.


![Beschreibung des Bildes](images/strips_total_wiring.jpeg)    

### Controls
The LED Bars work with any method of controlling the underlying WS2815 LED strips. Our controller is based on a nodeMCU (WT32-ETH01), which utilized [WLED](https://kno.wled.ge) for generating Effects or translating [DMX/Art-Net](https://en.wikipedia.org/wiki/Art-Net) from other sources.



We use a nodeMCU to connect the controller via ethernet. Power is supplied through a DC-DC Converter (12 -> 5V). 
To increase reliability, signals are boosted using a logic level shifter, which ensures a 5V signal from the 3V signal source of the nodeMCU. 
See here wiring diagram:

### Meownting
3D Model files and stl can be fund in /3d_models. It contains:

- Endcap
- Endcap Lid
- Mounting brace
- Mounting plate

Assembled, it works like this:
![mounting](/images/mount_me.gif)
Have fun mounting 

## Requirements to build
- 3D Printer
- WS2815 LED Strips (we use 60LEDs/m)
- Aluminium profiles with diffuser
- M4x12 screws and nuts
- threaded inserts
- DMX Male and Female connectors
- 3 pronged wire 6mm outer dimater
- glue 
  - to connect 3D printed parts to aluminum bars (we used epoxy)
  - to connect LED strips to aluminum bars (we used double sided gel tape)


## Manufacturing

### Strip assemply




1. Print 3D parts
2. put nuts & threaded inserts in printed end pieces
3. cut aluminum profiles and diffusers to desired length
4. Epoxy printed parts to aluminum profile
5. Wire up male & female DMX connectors to cables of preferred length
6. Solder cables to LED Strips of correct length
   1. very short de-insulation required!
    ![cable length](images/soldering_led.png)
7. Glue LED Strips into aluminum profiles
8. screw 3D printed lid onto strip for wire strain relief
   1. 🚧 🚧 shit breaks here, be careful 🚧🚧
9.  Put diffuser on
10. test
11. celebrate 🎉

 Always wire up in Serial!

<table style="width:100%; border:0; margin:0; height: 300"><tr>
<td style="width:50%; border:0;"> <img src="/images/end-1.jpeg" alt="Drawing" style="width: 250px;"/><img src="/images/end_gap.jpeg" alt="Drawing" style="width: 250px;"/> </td>
<td style="width:50%; border:0;"> <img src="images/end-2.jpeg" alt="Drawing" style="width: 250px;"/><img src="/images/end_nogap.jpeg" alt="Drawing" style="width: 250px;"/> </td>
</tr></table>
Measuring and cutting precicely creates perfect seams!

![Beschreibung des Bildes](images/end_diffuser.jpeg)

### Mounting



### Constroller Assembly

#### Flash Wled to nodeMCU
Basically do [what WLED needs](https://kno.wled.ge/basics/getting-started/)

<table style="width:100%; border:0; margin:0; height: 300"><tr>
<td style="width:33%; border:0;"> <img src="/images/flash_wled3.jpeg" alt="Drawing" style="width: 250px;"/> <img src="/images/flash_wled4.jpeg" alt="Drawing" style="width: 250px;"/> </td>
<td style="width:33%; border:0;"> <img src="images/flash_wled2.jpeg" alt="Drawing" style="width: 250px;"/><img src="/images/flash_wled5.jpeg" alt="Drawing" style="width: 250px;"/>  </td>
<td style="width:33%; border:0;"> <img src="images/flash_wled1.jpeg" alt="Drawing" style="width: 250px;"/> </td>
</tr>
</table>

#### Wire up Controller

Look at [WLED schematics](https://kno.wled.ge/basics/getting-started/) for reliable reference!

<table style="width:100%; border:0; margin:0; height: 300"><tr>
<td style="width:33%; border:0;"> <img src="/images/node_1.jpeg" alt="Drawing" style="width: 250px;"/> <img src="/images/node_2.jpeg" alt="Drawing" style="width: 250px;"/> </td>
<td style="width:33%; border:0;"> <img src="images/logic_level_shifter.jpeg" alt="Drawing" style="width: 250px;"/><img src="/images/logic_level_shifter2.jpeg" alt="Drawing" style="width: 250px;"/>  </td>
<td style="width:33%; border:0;"> <img src="images/DC_DC_Converter.jpeg" alt="Drawing" style="width: 250px;"/> </td>
</tr>
</table>

![Beschreibung des Bildes](images/controller_wiring.jpeg)
