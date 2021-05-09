
# releases

These releases are compiled on an ad-hoc basis and have been tested on the MiSTer Next core and ZEsarUX emulator (9.2)

For the latter, please use the nex file that ends in "_em"; this binary is assembled slightly differently to get around some bugs in the emulator, namely ULA hardware scrolling.

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
