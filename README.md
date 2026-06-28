# Soulm8 for [redacted] and Voron Trident
**"There is no Oitswilliam-made machine with no gimmicks."**
Soulm8 printer status indicator for [redacted] and Voron Trident.

It is just pronounced "soulmate", if you don't understand what Soulm8 is, say it, or refer to "m8".

## Features
Soulm8 is a printer status indicator made initially for Oitswilliam's upcoming 3D printer design that is based of Voron Trident with FrankenVoron Tridex, but because of the keyword *based of Voron Trident*, it is also compatible with Voron Trident.

### Status
Soulm8 uses pulsing indications for status. Note that when the status is off, then it is idle.
* None - idle or power off
* Amber yellow, blinking quickly and delay - printing
* Orange, blinking - paused, attention needed

## Bill-of-materials
* 2cm Neopixel RGB strip (100pc/m)
* M3x16mm FHCS countersunk, BHCS or SHCS
* The cables (2464 26AWG recommended), see wire requirement section on how to cut to length.

## Hardware and software requirements
### Hardware
The printer must be Voron Trident or similar that uses 2020 extrusion, support for 1515 and other 3D printers with stationary gantry are considered.

Mounting on other forms (i.e. Voron 2) work, but is not optimized.

### Software
Because we are lazy and we don't need to be primitive since we can install [Klipper LED effect add-on by Julian Schill](https://github.com/julianschill/klipper-led_effect) that I've used almost five years ago since V2.3347, Soulm8 is easy to install.

Be noted that the Soulm8 LED status require such add-on.

## Wire requirement
The cable is recommended to be shielded, 2- to 3-wire and the wire must be at least 26AWG.
* Shield connects to ground,
* Red connecs to 5V,
* Unless if only containing 2-wire, anything else connects to data pin.
### Cable length guide
* (X distance / 2) + 10mm + Y distance + (Z distance * 1.5) + 40mm + (Y distance * .8) = raw wire length ≈ rounded-off cable length in mm
* For example, if XYZ distances are all 250, then the value is (250 / 2) + 10 + 250 + (250 * 1.5) + 40 + (250 * .8) = 1000 and the Soulm8 cable length is that, 1000mm.

## Hardware installation
1. Feed the wire to the third cutout (second square, slightly smaller square) of soulm8_trident_shell.stl.
2. Remove the insulation at around 2cm of length.
3. Cut the LED strip to around 2cm, if using LED strip.
4. Attach the LED strip to soulm8_trident_indicator_unit.stl
5. Assemble the unit. Place soulm8_trident_indicator_unit.stl to soulm8_trident_shell.stl, and then secure them with soulm8_trident_wire_cover.stl.
6. Install Soulm8 hardware to the printer. The wire must face right (if the screw is on left) or installation will be conflicted on itself.
7. Feed the connector end of Soulm8 LED cable to the top-center of the bed (if it is), then to the bed cable chain, and then below deck.
8. Connect Soulm8 LED cable to the MCU with a free signal, 5V and ground pin.
9. Organize Soulm8 LED cable and attach several (at least 3, one front-left, and two center-right) soulm8_cable_organizer_piece.stl to the extrusion. 

## Macro modifications
Manual implementation is needed for Soulm8 to function. Soulm8 is made-optimized for [Non-motion MCU](https://github.com/Bunny350/Non-motion-MCU) but the pin can be changed to your decision. Check out soulm8.cfg for exact software installation. 
