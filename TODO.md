# TODO
### Next Jobs
- Get rudimentary file system up and running (ESXDOS?)
- Stub AY sound support
- Keyboard repeating
### Known Bugs
- The circle command does not clip correctly
- Can only set foreground colour of text in Mode 1
- Plot modes 1-5 do not work in Mode 1
- Cannot set RTC by assigning to TIME$
- No cursor in MODE 1
- Editor scrolls incorrectly when editing at bottom of screen
- COPY mode does not work after the screen has scrolled
### Fixed Bugs:
#### Version 0.04
- OLD does not restore a program after NEW
- INPUT does not return a value
- LD A,(IX) throws a syntax error in the assembler
- Add line editing functionality
- Set FLASH and BRIGHT with GCOL
