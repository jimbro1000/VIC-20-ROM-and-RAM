# VIC-20 Internal ROM Replacement and RAM Expansion #

This repository contains the design for a PCB to replace the
basic and kernel ROMs in a Commodore VIC-20. As a bonus the
board can also carry up to 32K of RAM to expand the memory
capacity internally without the need for RAM expansion 
cartridges.

## ROM Replacement

The board is designed to use 27c64 EPROMs to replace the
two core masked ROMs. It is expected to replace both - 
although it is possible to replace just one and will 
work with only one and it doesn't matter which, although
it is far more likely that it will be the kernel ROM
as these seem to be less reliable.

Binary images for the BASIC and Kernel ROMs can be
found here: [http://www.zimmers.net/anonftp/pub/cbm/firmware/computers/vic20/](http://www.zimmers.net/anonftp/pub/cbm/firmware/computers/vic20/)

## RAM Expansion

The board has four positions for RAM ICs, it is not
necessary to fill any or all of these posiitons but
they must be populated from right to left (any
unused positions must be to the left).

### Selecting RAM Size

The board includes a bank of 4 DIP switches that can be
used to enable or disable RAM ICs. As with populating the
RAM ICs on the board the switches should be used in
descending order to reduce capacity, from left to right.

If a RAM expansion cart is to be used as well it is important
to avoid conflicts by disabling the appropriate RAM ICs.
This is even more important if the cartridge has a ROM
assigned to one of those slots.

## Assembly

The interactive BOM can be found in this repositiory:
[./bom/ibom.html](bom/ibom.html)

The trickiest part of the assembly is fitting the connecting
pins on the lower side of the board. These need to be 
accurately aligned to ensure they will fit the main board
correctly. It is recommended to use turned pin headers cut
to the right length. Once soldered in place the pins 
extending on the upper side of the board will need to be 
trimmed down to allow sockets to be fitted over them.

The rest of the board should be straight forward assembly.

For J1 (connections to the cartridge port), it is recommended
to use pin headers or a pin socket so that the board can
be removed without significant effort.

## RAM Only Expansion ##

If you *only* want to utilise the RAM expansion capability
of the board it will still need a connection to the main
board through one of the ROM positions. To do this the
original ROM must be removed but can be reattached to 
the top of the expansion board. In this situation do not
fit the socket for an EPROM and solder the original ROM
to the exposed pins connecting to the original ROM
position. This can be tricky and is best done by bending
the ROM chip legs in slightly so that they sit inside
the exposed pins on both sides, but still touching. This
should simplify the soldering task.

## Installation ##

### ROM Operation

The board is installed by soldering the pins on the 
bottom of the board into the original ROM positions of
the main board.

### RAM Operation

In addition to the connections under the board the
RAM Expansion requires additional connections to be
made. The expectation is that these will be to the
exposed pins of the cartridge port.

The expansion board has 5 pins at the top that 
need to be connected (from left to right) to
pins 18 (CRW), 13, 12, 11 and 10 (BLK5, 3, 2 and 1).
These provide the Read/Write and enable signals
to the RAM ICs, without these connections the
RAM will not operate.

The connections to the cartridge port can be
soldered to those pins or through the use of
wiring probes/clips. Soldered connections
should prove more durable but makes the install
more permanent.