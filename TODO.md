# TODO
### Next Jobs
- Stub AY sound support
### Known Bugs / Missing Features
- The graphics primitives (line, circle, triangle) do not clip properly
- The graphics commands may not work correcly with a vertical scroll offset
- Plot modes 1-5 and Point do not work in Mode 1
- Cannot set RTC by assigning to TIME$
- Timestamp not set in saved files
- No attempt to check whether a loaded file will fit in memory
- The DIR outputs file size in bytes; be good to have human readable units (bytes/KB/MB)
### Fixed Bugs / New Features
#### Version 0.08
- Mode 2 (320x240) now implemented
- Cursor is now a sprite and works in all modes
- Editor refactored to fix many bugs, including:
	- Editor scrolls incorrectly when editing at bottom of screen
	- Unable to type in COPY mode
#### Version 0.07
- Added *DELETE, *MKDIR, *RMDIR and *DRIVE commands
- More specific errors in exsDOS are now displayed
- exsDOS now shifts temporarily to 28Mhz CPU to fix errors running on MiSTer
#### Version 0.06
- Scrolling in Mode 1 now uses the background colour to fill
- SAVE, LOAD and CHAIN commands now implemented
#### Version 0.05
- Rudimentary file system up and running
- Fixed debounce on CAPS LOCK or EDIT
- INKEY$ no longer waits for input
- Added keyboard repeating
- When in COPY mode, the cursor now wraps correctly at end of screen
- COPY mode now stops inserting when buffer is full
- ESC now exits AUTO line numbering
- POINT code moved to next_graphics.z80
#### Version 0.04
- Added line editing functionality
- OLD now restores a program after NEW
- INPUT statement now returns a value
- LD A,(IX) no longer throws a syntax error in the assembler
- GCOL now sets FLASH and BRIGHT
- Line editor now works in MODE 1
- Background colour can now be set in Mode 1
- COPY mode now works after the screen has scrolled
#### Version 0.03
- Z80 assembler output now tabulated correctly
- Spectrum (C) symbol now remapped as ASCII 0xA9
