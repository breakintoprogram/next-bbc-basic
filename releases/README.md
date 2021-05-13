
# releases

These releases are compiled on an ad-hoc basis and have been tested on the MiSTer Next core and ZEsarUX emulator (9.2)

For the latter, please use the nex file that ends in "_em"; this binary is assembled slightly differently to get around some bugs in the emulator, namely ULA hardware scrolling.

##### 20210513: Version 0.02
- Added Z80N instrructions to Z80 assembler - see [test_assembler_Z80N.bbc](../tests/test_assembler_Z80N.bbc) for example test code
- Bug fixes

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
