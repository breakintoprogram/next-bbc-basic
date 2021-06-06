# TODO
### Next Jobs
### Known Bugs / Missing Features
- Cannot COPY characters in Mode 1 or 2
- Plot modes 1-5 and Point do not work in Mode 1
- Cannot set RTC by assigning to TIME$
- Timestamp not set in saved files
- No attempt to check whether a loaded file will fit in memory
- The DIR outputs file size in bytes; be good to have human readable units (bytes/KB/MB)
- ESC does not appear to work whilst waiting for input in GET statement (check INKEY too)
- Cursor going missing at bottom of screen in Mode 1 and Mode 2 (only seen on MiSTer)
- SOUND queue loop does not check for Escape
### Fixed Bugs / New Features
#### Version 0.09
- Fixed clipping in line, circle and triangle graphics primitives
- Fixed issue with negative plot coordinates
- Fixed issue with scrolling and graphics primitives in Modes 0, 1 and 2
- Added AY sound support
#### Version 0.08
- Mode 2 (320x256) now implemented
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
