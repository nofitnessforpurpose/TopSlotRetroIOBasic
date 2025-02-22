# Top Slot Retro IO Basic

A minimal Top Slot hardware interface for Organiser II (all family) devices. The intention to allow support for various I/O devices using 5 Volt signals. The design fits a classic Organiser II Top Slot Case (See all notes).
<BR>
<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotRetroIOBasic/blob/main/images/TSRIOB-01.jpg?raw=true" width="400px" alt="PSION Organiser II Top Slot Basci I/O Interface. Image copyright (c) 10 November 2024 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>

[![Organiser](https://img.shields.io/badge/gadget-Organiser_II-blueviolet.svg?%3D&style=flat-square)](https://en.wikipedia.org/wiki/Psion_Organiser)
[![GitHub License](https://img.shields.io/github/license/nofitnessforpurpose/TopSlotRetroIOBasic?style=flat-square)](https://github.com/nofitnessforpurpose/TopSlotCase/blob/main/LICENSE)
[![Maintenance](https://img.shields.io/badge/maintained%3F-yes-green.svg?style=flat-square)](https://github.com/nofitnessforpurpose/TopSlotCase/graphs/commit-activity)
![GitHub repo size](https://img.shields.io/github/repo-size/nofitnessforpurpose/TopSlotRetroIOBasic?style=flat-square)
[![Static Badge](https://img.shields.io/badge/format-GERBER-blue?style=flat-square)](https://en.wikipedia.org/wiki/Gerber)

<br>  
All the files are required for a complete assembly.  
<BR>
 - The default code format is <a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Open_Programming_Language">OPL</a> or 6303 Assembler as flat text files.
<BR>
 - The default repository format is STEP (<a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/ISO_10303"> ISO 10303</a> ) due to its high fidelity.  
<BR>
 &nbsp;&nbsp;&nbsp;&nbsp;{ STL files are surface geometry as opposed to solid model representations, often containing export processing artifacts }. <br>  
 - The default repository format for PCB files is <a targer="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Gerber_format">GERBER</a> .
<BR>

<BR>
<a target="_blank" rel="noopener noreferrer" href="https://www.freecad.org/" > FreeCAD </a> may prove suitable for viewing, handling and, if desired modifying STEP files.
<BR>
<a target="_blank" rel="noopener noreferrer" href="https://www.kicad.org/" >KiCad </a> may prove suitable for viewing GERBER files.
<BR>
<BR>

## Implementation
The design presents a classic minimal, design reference based, interface to the Top Slot hardware of a PSION Organiser II family of devices. The 4 layer PCB dimensions (38.0 x 43.6 mm) are ideally suited to low cost manufacture. The 4 layer PCB design provides improved EMC performance over two layer implementations. Whilst the PCB space claim is intented to be suitable for a classic <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase">Top Slot Case </a> and construction is through hole PCB based for ease of assembly.

<BR>

### Device Power Source  
A classic Barrel Jack (5.5 mm outer, 2.0 mm pin) connector for the ~10.4 Volt 175 milli Amp center positive pin power supply is located to be compatible with the classic Top Slot Case. The Barrel Jack connections are brought to 2 header pins on the left of the PCB to permit alternate power sources to be readily accomodated. (This is the same connector used on the classic Arduino Uno and Mega boards).   

<BR>

### Input / Output    
4 channel buffered Input / Output configuration, comprising 2 Inputs being bits D2 & D3 and 2 Outputs being bits D0 & D4 along with switched 5 Volts and Ground.

<BR>

### Data lines  
An 8 way resistor pack is wired to all slot data lines D0 through D7, so as to permit ready modification of the bits used for an I/O interface implementation. The 8 way resistor pack was selected as it is used on other <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose?tab=repositories">designs</a>. As a data pack is implied, though not mandatory, due to the ommision of an on board ROM the resistor pack may not be required. As Data Packs in side slots contain equivalent circuitry to manage data bus impedance. Though EMC performance will differ.  
<BR>
If found more convenient than a resistor pack, individual 47k Ohm resistors might be vertically mounted and commoned to RN1's common connection (Pin 1) whilst retaining compatability with the Top Slot Case. This has the advantage of thus requiring only 1 resistor part number / value for the implementation, as 47k Ohm resistors can be fitted to all resistor locations.

<BR>

### Decoupling  
Decoupling capacitor locations are avilable for the board and or digital I/C's. It has been found the noise level on the implementation to be low and at the point of testing no anomalous behaviours measured or observed.  
<BR>
Decoupling capacitance should be kept to a minimum, as this respresents a power drain during slot power up events. 47 nF is recomended for C1 and or C2 as preferred, though a single 100 nF (0.1uF) fitted to C1 was found to provide acceptable performance.

<BR>

### Connections  
Connection for external signals is 5 Volt TTL via a 0.1" header compatible connection J3.  

| PIN | Description  | Func | FTDI Cable  | C1 Cable    |
| --- | ------------ | ---- | ----------- | ----------- |
| 1   | +5 Volts     | +5 V | N.C. (Red)  | N.C. (Red)  |
| 2   | 0 Volts      | 0 V  | Black       | Black       |
| 3   | D3 - Input   | TxD  | Orange      | Green       |
| 4   | D2 - Input   | RTS  | Green       | Yellow      |
| 5   | D0 - Output  | CTS  | Brown       | Blue        |
| 6   | D4 - Output  | RxD  | Yellow      | White       |

Table of example connections to 5 Volt USB Serial adaptor cables  
<BR>
<BR>

## Use Case  
<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotRetroIOBasic/blob/main/images/TSRIOB-09.png?raw=true" width="300px" alt="PSION Organiser II Top Slot Basci I/O Interface. Image copyright (c) 08 December 2024 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>
Though not the principle goal, an immediate advantage of the selected arrangement is the device supports 'Out of the box' 5 VOLT TTL RS232 hardware support capabilty. As the I/O lines are selected from the internal on microcontroller RS232 hardware lines. Further, it is code compatible with the classic COMMS LINK adaptor (though of course has no on board COMMS LINK ROM). It is anticiapted this device can be readily built and code reside on internal memory (A:) or a Side Slot (B: or C:) location.  
<BR>
<BR>
*** IMPORTANT NOTE - DO NOT CONNECT DIRECTLY TO <a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/RS-232#Voltage_levels">RS232 VOLTAGE LEVELS</a> - IT WILL DEGRADE THE DEVICE ! ***  
<BR>
<BR>
Testing indicated good compatability, with the exception of DTR i.e. hardware not implemented, with <a href="http://www.lostgallifreyan.net/Software/ORG-Link/ORG-Link.htm">ORG-Link</a> when coupled with an <a href="https://ftdichip.com/products/ttl-232r-5v/">FTDI 5 Volt to RS232 Convertor</a> connected to an IBM PC compatible system.

A minimal configuration requires:  
- 4 layer PCB
- CD4011UBE  (SN74HC00N is an alternate part)
- SN74HC125N
- 1N4148 Diode  
- 47K Resistor  (or 4k7)
- 2 x 8 way Right angle header (~8 mm engagement length)

An advantage of using the approach as applicable to a COMMS LINK adaptor, is that the charge pump necessary for legacy compatability in the classic COMMS LINK adaptors is not present and considerable reductions in power are therefore achieved. Making it practicable to operate for considerable periods without external power source, even when high capacity batteries are not fitted to the Organiser. Power for an FTDI interface chip included in the FTDI USB connector is sourced from the host computer, futher reducing power drain on the Organiser device.  

Other 5 Volt to USB adaptors may function, no testing has been performed on other devices.   

<BR>

## Considerations
Models or files makes no accomodation for manufacturing tolerances, process or material - see Notes below.  

The original male 8 way 2 row top slot header style connector (marked <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase/blob/main/images/MXS-70224-02%20(2).jpg">MXS 70224</a>) may have included a custom pin support moulding. Data from a parts list kindly indicated in this <a href="https://www.organiser2.com"> hardware forum</a> seemed to confirm this theory. Readily available 8 way 2 row header connectors tend to have smaller pin support mouldings. The effect of using pin headers with smaller moulding is to permit the PCB to displace vertically in the slot guide channel, resulting in poor alignment with the mating female connector and potential insertion difficulty. There are a number of mitigations, such as changing the height of the male header connector in the PCB and adding material to support the top of a smaller male header pin support moulding. The precise accommodation will depend on your selected pin header moulding. Potentially <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase-2/">this</a> case may be of assistance.  

Connecting any device which has not undergone thorough testing, will lead to irreversible degredation!  

<BR>

## Questions / Discussion
See <a target="_blank" rel="noopener noreferrer" href="https://www.organiser2.com/"> Organiser 2 Hardware </a> forum, though see note below first.

<BR>

## Please note:  
All information is For Indication only.
No association, affiliation, recommendation, suitability, fitness for purpose should be assumed or is implied.
Registered trademarks are owned by their respective registrants.
