# Purpose #

This is a KiCad project that documents a simple half-bridge circuit, complete with driver.  The
circuit includes room for two TO-220 MOSFETs, two snubber circuits.  It has two logic-level inputs 
which will turn on the upper and lower MOSFETs.

# Details of Operation #

## Power Supply ##

If 10V < V<sub>BATT</sub> < 20V, then the jumper at P2 may be connected so that the
[FAN7842MX](https://www.fairchildsemi.com/datasheets/FA/FAN7842.pdf) is properly supplied.

If V<sub>BATT</sub> < 10V or V<sub>BATT</sub> > 20V, then the user must supply a voltage
between 10V and 20V to the circuit using pin 1 of P1.

## PWM Frequency ##

The circuit is intended to operate as a complete half-bridge using Pulse Width Modulation (PWM) on
the high side AND the low side.  When the upper MOSFET is being operated, it must be operated
synchronously with the lower MOSFET in order to charge the bootstrap capacitor.  The minimum recommended
PWM frequency is 10kHz.

When only the lower MOSFET is being operated, then the upper MOSFET input may be held low while the
lower MOSFET is operated at any frequency desired, including DC.

## Specifications ##

The circuit is intended to operate at a maximum voltage of ~35V and 5A, but these are limitations of
the components and not of the circuit board.  The board - with the proper capacitors and MOSFETs -
should be able to operate as high as 200V at a current of up to 20A.

## Connections ##

### Breadboard ###

If the breatboard power rails are between 10V and 20V and the expected current is under 1A, then P1,
P2, and P3 can be populated on the underside of the board and simply plugged into the breadboard.

When the voltage is outside of the 10V to 20V range, then only pins 1, 2, and 3 of P2 should be
populated and plugged into the breadboard.  The 10V-20V should be supplied to the board through
pin 1 of P1.

### Screw Terminals ###

If P2 is not populated, then power may be supplied through the screw terminals on P4.

# Why Do This? #

I know that there are lots of these sorts of circuits available, but I am continually finding myself
re-drawing this schematic for different circuits.  By placing all of the components for the half-bridge
on one circuit, I have a flexible and extendable starting point for a host of circuits.  Applications
include:

 * DC-DC conversion
 * DC motor drives
 * BLDC motor drives
 
I had a look around and didn't see anything quite like it on Tindie nor a couple of other sites that
I frequent.  World, here ya go.
