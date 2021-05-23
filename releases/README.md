
# releases

These releases are compiled on an ad-hoc basis and have been tested on the MiSTer Next core, ZEsarUX emulator (9.2) and CSpect (2.13.01)

If you are using ZEsarUX, please use the nex file that ends in "_em"; this binary is assembled slightly differently to get around some bugs in the emulator, namely ULA hardware scrolling.

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
