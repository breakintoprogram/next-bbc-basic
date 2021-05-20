# manual

The Next version is near identical to the original language, with the following changes:

## Editor

A line editor is provided, that allows the user to enter a line of code up to 255 characters long. A cursor can be moved around this line, and text can be deleted or inserted at the current character position.

A copy mode is provided, by pressing EDIT (Shift+1). When in copy mode, the cursor can be moved around the screen. Pressing Delete (Shift+0) will copy the character under the cursor into the current line. Pressing EDIT or CR will exit copy mode.

## Assembler

The assembler has been extended to handle Z80N instructions.

See [test_assembler_Z80N.bbc](tests/test_assembler_Z80N.bbc) in the folder tests for a usage example.

## BASIC

The following statements differ from the BBC Basic standard:

### PUT port,value[,type]

An additional optional parameter, type, has been added.

- 1: write out value to a NEXTREG register
- 0: write value to a Z80 port. 

### GET(port[,type])

Like PUT, this takes an optional type parameter to read from NEXTREG registers

### PLOT type,x,y

The only plot modes supported currently are:

- PLOT 0, X, Y: Draw a line from last plot position to X, Y
- PLOT 64, X, Y: Plot a point
- PLOT 80, X, Y: Draw a filled triangle. The other two points are the last two plot positions.
- PLOT 144, 0, R: Draw a circle of radius R. The center position is the last plot position

### MODE n

Two modes supported:

- MODE 0: ULA mode (Normal Spectrum 256x192 Graphics)
- MODE 1: Layer 2 mode (256 x 192, 256 colours per pixel)

### COLOUR n[,type]

An additional optional parameter, type, has been added. If not specified, will default to 0.

- 0: Set colour as BBC Standard; add 128 to set paper colour.
- 1: Set foreground (ink) colour
- 2: Set background (paper) colour
- 3: Set border colour
- 4: Set bright (Mode 0 only)
- 5: Set flash (Mode 0 only)

### GCOL mode, colour[, type]

Sets the graphic colour, as per COLOUR

Mode values for MODE 0 is currently one of the following:
- 0 and 1 set the pixel
- 2 and 6 clear the pixel
- 3 and 4 invert the pixel
This is an attempt to stick to the BBC BASIC standard with 1-bit graphics

Mode for MODE 1 should work as per BBC Basic specifications but currently only supports 0 and 6 due to a memory mapping issue I need to resolve.

### VDU

The VDU command is a work-in-progress with a handful of mappings implemented

## STAR commands

The star commands are all prefixed with an asterisk. Numeric parameters can be specified in hexadecimal by prefixing with an '&' character.

### TIME

Output the current RTC time (if RTC fitted) in BBC Master format.

The time is also available in the system variable TIME$

### TURBO n

Will set the Next CPU turbo mode:
- 0: 3.5Mhz
- 1: 7Mhz
- 2: 14Mhz
- 3: 28Mhz

### MEMDUMP start,len

List contents of memory, hexdump and ASCII.

### FX n

- 19: The only FX command supported - waits for the horizontal sync

## Other considerations

I use ULA hardware scrolling, so the top-left screen address is not guaranteed to be 0x4000, likewise the attributes address at 0x5800.
