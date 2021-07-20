
# releases

These releases are compiled on an ad-hoc basis and have been tested on the MiSTer Next core, ZEsarUX emulator (9.3 Beta 1) and CSpect (2.14.03)

#### Using with ZEsarUX

Please make sure you use the latest version of ZEsarUX (9.3 Beta 1 at time of writing). Earlier versions are missing a couple of features that have been introduced into later cores, ULA scrolling and relative Layer 2 page offset.

I would also recommend you copy the nex file to the img file and launch from the Next browser. ZEsarUX does not initialise the Next correctly if the nex file is dragged into the emulator or loaded using Smart Load. This is by design, but will prevent the disk commands from working. I would recommend this method anyway.

##### 20210720: Version 0.16
- Implemented a handful of page &FF calls
	- OSBPUT
	- OSBGET
	- OSWRCH
	- OSBYTE (0x00, 0x13, 0x14, 0x80)
- Added ADVAL function
- Added Kempston mouse support (via ADVAL function)
- Added *FX 11 to set keyboard auto-repeat delay
- Added *FX 12 to set keyboard auto-repeat period
- Refactoring and bug fixes
##### 20210713: Version 0.15
- Fixed bug in PUTCSR; TAB(X,Y) now sets Y coordinate correctly
- Modifications to GET and PUT
	- Added GET(x, y) and GET$(x, y) to read character from screen position (x, y)
	- Changed GET(n, 1) to GET(n OR &10000)
	- Changed PUT(n, 1) to PUT(n OR &10000)
- Added support for UDGs
	- *FX 20: Reserve space for UDGs in RAM
	- VDU 23, char, b0, b1, ..., b7: Define a character
##### 20210706: Version 0.14
- RAM contention is now switched off for 3.5Mhz CPU speed
- GCOL modes for PLOT now work in Mode 3
- Data file I/O now implemented:
	- OPENIN, OPENOUT, OPENUP, CLOSE#
	- INPUT#, PRINT#
	- EOF#, PTR#, EXT#
##### 20210622: Version 0.13
- COPY characters now works in Modes 1, 2 and 3
- Set all graphics to use common viewport (1280x1024) with origin at bottom left, like BBC Micro
- All BASIC graphics tests updated in tests folder
- Added support for VDU 29 (setting the graphics origin)
- CLG now works
##### 20210614: Version 0.12
- Fixed bugs in Clear_Screen:
	- Background colour now set correctly in Mode 3
	- It was clearing 18 16K banks rather than 3 (Mode 1) or 5 (Mode 2 or 3)
	- CLG now works
- Fixed bug in Mode 3 horizontal line routine (for filled triangles)
- Modes 1, 2 and 3 now have a Spectrum palette in first 16 colours
##### 20210613: Version 0.11
- Fixed bug in check for zero-length lines
- Mode 3 implemented (640x256, 80 column text)
##### 20210609: Version 0.10
- ESC handled correctly on interrupt (can break out of LIST, for example)
- ESC now breaks out of GET($) and SOUND command
- Plot modes 1-5 and Point now work in Modes 1 and 2
- Fixed disappearing cursor bug at bottom of screen in Mode 1 and Mode 2
- Fixed default palettes in all modes
- Fixed zero length line bug

##### 20210606: Version 0.09
- Fixed clipping in line, circle and triangle graphics primitives
- Fixed issue with negative plot coordinates
- Fixed issue with scrolling and graphics primitives in Modes 0, 1 and 2
- Added SOUND command

##### 20210603: Version 0.08
- Mode 2 (320x240) now implemented
- Cursor is now a sprite and works in all modes
- Editor refactored to fix many bugs, including:
	- Editor scrolls incorrectly when editing at bottom of screen
	- Unable to type in COPY mode

##### 20210525: Version 0.07
- Second drives can now be accessed with *DRIVE command
- Added *MKDIR, *RMDIR, *DELETE
- Added *LOAD, *SAVE for loading and saving memory blocks
- Added the alias *DIR for *CD
- Added the alias *ERASE for *DELETE
- Now shifts automatically to TURBO 3 when doing DOS writes
- Meaningful DOS error messages

##### 20210524: Version 0.06
- Added disk operations LOAD, CHAIN and SAVE

##### 20210523: Version 0.05
- Added disk operations *CAT and *CD
- Improved editor with key repeat and better debounce
- A handful of Z80N optimisations in the core language routines
- Bug fixes

##### 20210520: Version 0.04
- Added filled triangle graphics routine
- Improved line editor

##### 20210516: Version 0.03
- Added MODE command
- Added line and circle graphics routines
- Star commands can now take decimal or hex values
- Graphics routines for Layer 2 and ULA now split into separate files

##### 20210513: Version 0.02
- Added Z80N instructions to Z80 assembler - see [test_assembler_Z80N.bbc](../tests/test_assembler_Z80N.bbc) for example test code

##### 20210510: Version 0.01
- Turbo mode command renamed from *RUN to *TURBO
- Added RTC support - time can be accessed via *TIME or variable TIME$
- Added VDU command support for cursor control, CLS, COLOUR, CLG, GCOL and PLOT
- General tidy up of the source code

##### 20210509: Initial Version
- Implemented key scanning and output routines
- Modified PUT and GET to support writing and reading NEXTREG registers directly
- Implemented COLOUR, GCOL, CLS, GCLS
- Started implementating PLOT and FX commands
- Started implementing MODE
- Added *RUN to set turbo mode
- Added *MEMDUMP to help in debugging    

Dean Belfield
www.breakintoprogram.co.uk
