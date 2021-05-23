# TODO
### Next Jobs
- Stub AY sound support
### Known Bugs
- The graphics primitives (line, circle, triangle) do not clip
- Plot modes 1-5 and Point do not work in Mode 1
- Cannot set RTC by assigning to TIME$
- No cursor in MODE 1
- Editor scrolls incorrectly when editing at bottom of screen
- Unable to type in COPY mode
### Fixed Bugs:
#### Version 0.05
- Get rudimentary file system up and running
- Fixed debounce on CAPS LOCK or EDIT
- INKEY$ is waiting for input
- Added keyboard repeating
- When in COPY mode, the cursor does not wrap correctly at end of screen
- COPY mode does not stop inserting when buffer is full
- Unable to exit AUTO line numbering
- POINT code needs moving to next_graphics.z80
#### Version 0.04
- Added line editing functionality
- OLD does not restore a program after NEW
- INPUT statement does not return a value
- LD A,(IX) throws a syntax error in the assembler
- Unable to set FLASH and BRIGHT with GCOL
- Line editor does not work at all in MODE 1
- Can only set foreground colour of text in Mode 1
- COPY mode does not work after the screen has scrolled
#### Version 0.03
- Z80 assembler output now tabulated correctly
- Spectrum (C) symbol now remapped as ASCII 0xA9
