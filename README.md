# TopSlotRetroIOBasic

A minimal Top Slot hardware interface for PSION Organiser II (all family) devices. The intention to allow support for various I/O devices using 5 Volt signals. The design fits a classic PSION Orgnanser II Top Slot Case (See all notes).
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
All the files are required for a complete assembly. The default repository format is STEP (<a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/ISO_10303"> ISO 10303</a> ) due to its high fidelity.  { STL files are surface geometry as opposed to solid model representations, often containing export processing artifacts }. <br>  
<br>  
<br>  
  The default repository format for PCB files is <a targer="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Gerber_format">GERBER</a> .
<br>

<br>  
<a target="_blank" rel="noopener noreferrer" href="https://www.freecad.org/" > FreeCAD </a> may prove suitable for viewing, handling and, if desired modifying STEP files.
<br>
<a target="_blank" rel="noopener noreferrer" href="https://www.kicad.org/" >KiCad </a> may prove suitable for viewing GERBER files.
<br>

## Use Case
The design presents a classic recomended interface to the Top Slot hardware. Though not the principle goal, an immediate advantage is that the device supports 'Out of the box' 5 VOLT TTL RS232 hardware support capabilty. As the I/O lines are selected from the internal on microcontroller RS232 hardware lines. Further, it is code compatible with the classic Comms adaptor (though of course has no on board RS232 ROM). It is anticiapted this device can be readily built and code reside on internal memory (A:) or a Side Slot (B: or C:) location.
<BR>
<BR>
*** IMPORTANT NOTE - DO NOT CONNECT DIRECTLY TO RS232 LEVELS - IT WILL DEGRADE THE DEVICE ! ***  
<BR>
<BR>
Testing indicatged good compatability, with the exception of DTR i.e. hardware not implemented, with <a href="http://www.lostgallifreyan.net/Software/ORG-Link/ORG-Link.htm">ORG-Link</a> when coupled with an <a href="https://ftdichip.com/products/ttl-232r-5v/">FTDI 5 Volt to RS232 Convertor</a> connected to an IBM compatible computer.

A minimal configuration requires:  
- 4 layer PCB
- CD4011UBE  
- SN74HC125N
- 1N4148 Diode  
- 47K Resistor  
- 2 x 8 way Right angle header

An advantage of using the approach as applicable to a Comms adaptor, is that the charge pump necessary for legacy compatability in the classic Comms adaptors is not present and considerable reductions in power are therefore achieved. Making it practicable to operate for considerable periods without external power source, even when high capacity batteries are not fitted to the Organiser. Power for an FTDI interface chip  included in the FTDI USB connector is sourced from the host computer, futher reducing power drain.

Other 5 Volt to USB adaptors may function, no testing has been performed on other devices. 

## Considerations
Models or files makes no accomodation for manufacturing tolerances, process or material - see Notes below. 

The original male 8 way 2 row top slot header style connector (marked MXS 70224) may have included a custom pin support moulding. Data from a parts list kindly indicated in this <a href="https://www.organiser2.com"> hardware forum</a> seemed to confirm this theory. Readily avialable 8 way 2 row header connectors tend to have smaller pin support mouldings. The effect of using pin headers with smaller moulding is to permit the PCB to displace vertically in the slot guide channel, resulting in poor alignment with the mating female connector and potential insertion difficulty. There are a number of mitigations, such as changing the height of the male header connector in the PCB and adding material to support the top of a smaller male header pin support moulding. The precise accomodation will depend on your selected pin header moulding.     

Connecting any device which has not undergone thorough testing, will lead to irreversible degredation.

## Please note:  
All information is For Indication only.
No association, affiliation, recommendation, suitability, fitness for purpose should be assumed or is implied.
Registered trademarks are owned by their respective registrants.
