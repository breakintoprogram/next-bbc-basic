
# next-bbc-basic
A port of BBC Basic for Z80 to the Spectrum Next

### Why BBC Basic

The original version of BBC Basic was written by Sophie Wilson at Acorn in 1981. It was written in 6502 for the BBC Micro range of computers, designed to support the UK Computer Literacy Project.

R.T.Russell ported this to Z80, and this version has been ported to a number of Z80 based machines. [You can find a full history of BBC Basic on his website](http://www.bbcbasic.co.uk/bbcbasic/history.html).

Whilst I love Sinclair BASIC, I feel that BBC Basic addresses many of its shortcomings, including the clunky editor, variable name limitations for strings and arrays, and performance.

“Ah”, I hear you say. “I can load a BBC Micro Core in my Next to run BBC Basic”. Yes of course you can do that, and it is an excellent core. You will of course be restricted to BBC Model B hardware in doing so.

The advantage of running BBC Basic native on the Next is that it can potentially take advantage of the Next’s advanced graphics and sound capabilities; hardware sprites, Layer 2 graphics, multiple AY chips, and of course the legendary 28Mhz Turbo mode.

### The Challenges

The foundation of this port is R.T.Russell's original BBC Basic for Z80 code (for CP/M), with the CP/M specific code stripped out. This foundation code is just pure BASIC interpreter with no graphics, sound or file I/O support.

I will need to add all of that in, in a manner that befits both BBC Basic, and the features available to the Next that the language was not designed to handle, such as hardware sprites.

### Next Specific Modifications

The Next version is near identical to the original language, with the following changes:

###### PUT port,value[,type]

If type is 1 will write out to a NEXTREG register
If type is 0 will write to a Z80 port. 
Type is optional and will default to 0

###### GET(port[,type])

Like PUT, this takes an optional type parameter to read from NEXTREG registers

###### PLOT type,x,y

Currently just plots a point at screen positions X (0 to 255) and Y (0 to 191) on the ULA layer using the current graphics colour and mode set by GCOL.

Type is usually the plot type (relative, absolute, plot, line, etc), but is currently ignored. Only plotting points is supported at the moment.

###### COLOUR n

Sets the text colour. 0 to 7 sets the INK colour, 128 to 135 sets the PAPER colour. Currently no support for BRIGHT or FLASH

###### GCOL mode, colour

Sets the graphic colour. INK and PAPER are set using the same values as the COLOUR command. Mode is currently one of the following:
- 0 and 1 set the pixel
- 2 and 6 clear the pixel
- 3 and 4 invert the pixel
This is an attempt to stick to the BBC BASIC standard with 1-bit graphics

### STAR commands

###### *RUN n
Will set the turbo mode (0: 3.5Mhz, 1: 7Mhz, 2: 14Mhz, 3: 28Mhz)
###### *MEMDUMP start,len
List contents of memory - start and len are in hex
###### *FX command support
- 19: The only FX command supported - waits for the horizontal sync

### Other considerations

- I use ULA hardware scrolling, so the top-left screen address is not guaranteed to be 0x4000, likewise the attributes address at 0x5800.

### Assembling

The code is written to be assmbled by the SJASMPLUS assembler. Details of the toolchain I use [can be found here on my website](http://www.breakintoprogram.co.uk/computers/zx-spectrum-next/assembly-language/z80-development-toolchain).

Please note that you will need to set the conditional assembly flag BUILD_EMULATOR to 1 if you are assembling this for ZEsarUX. It uses out-of-date register numbers for the ULA hardware scrolling.

Every endeavour will be made to ensure the code is stable and will assemble, yet as this is a work-in-progress done in my spare time there will be instances where this is not the case. Please do not raise an issue in GIT, I'm more than likely aware of this!

### Releases

I'll dump significant updates as executable nex files in the releases folder

### License

This code is distributable under the terms of a zlib license. Read the file COPYING for more information.

The code, as provided by David Given (dg@colark.com), and originally written by
R.T. Russell has been modified slightly to compile in sjasmplus, and the CPMish
code has been removed as this version is not going to run CP/M.

- GLOBAL and EXPORT directives have been removed and any global labels prefixed with @
- All source in z80 files is now enclosed in MODULES to prevent label clash
- A handful of '"' values have been converted to 34, and commented with ASCII '"'
- The patch file has been modified
	- The function PUT has been moved from exec to patch
	- The function GET has been moved from eval to patch
- A build.z80 file has been added; this includes all other files and is the file to build
- The top-of-file comments have been tweaked to match my style

Other than that, the source code is equivalent to the code originally authored by R.T.Russell, downloaded on David Given's website: 

http://cowlark.com/2019-06-14-bbcbasic-opensource/index.html

Any Spectrum Next specific code is clearly marked in z80 files prefixed with "next_". Any additions or modifications I have made to port this to the Next I have released under the same licensing terms as the original code and, when R.T.Russell's original source files need to be modified to accomodate this, the changes are clearly commented in the code.

Dean Belfield
www.breakintoprogram.co.uk
