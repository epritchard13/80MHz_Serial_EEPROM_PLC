## Members
Eddie Pritchard, Computer Engineering Student (2024)
epritchard@vt.edu

## Mentor
Ethan James

## Current Status
ORDERING PARTS

## Project Overview

This project is a spin-off of the 93c46a spi eeprom PLC I designed. While working on reducing the chip count required to read from a specified address of the 93c46a, I came across the M95Pxx series ST spi eeproms which have up to 4Mbytes capacity. 
The addressing requires 22 bits, pushing the eeprom into the four-byte-spi range. The four-byte-spi command chips are unique because a circuit may be devised to feed the serial output of the M95Pxx serial eeprom back into the input of the command build shift registers.
Given that there must be four eight bit command build registers to complete the 22b+2dummy bit + 8b command (32b) read sequence, a following 16cc may be used to shift the read data back into the first two SR. This first 16b read is the instruction.
If the instruction commands a jump (unconditional or not), then the serial eeprom is asked to shift out another 16 bits, then parallel load the code and MSB PISO shift registers, then reset and shift in 32 bits. This completes the jump and the next instr can be read.

## Educational Value Added

The above mentioned circuit is a turing complete PLC using 5 to 6  74-series chips. Conditional branching makes the PLC turing complete assuming that other operations drive the conditional branch conditions. 
If this circuit runs at the max speed of the shift registers (74hc595 and 74hc165) and the M95Pxx serial eeprom, then the instruction unit may fetch new instructions at 5MHz (16b parallel). The educational value added by this project includes:
 - High Speed PCB routing (80MHz)
 - Assembler design of the PLC code assembler
 - Soldering of UDFN exposed pad / SMD

## Tasks

Place purchase request for parts and PCB
populate PCB


## BOM + Component Cost

M95Pxx (Purchase 5 at $2 per)
PCB    (Purchase 5 at $5 per) I WILL BUY
74hc595 (Purchase 10-25 at $0.25 per)
74hc165 (Purchase 10-25 at $0.50 per)

## Timeline

PO placed 11/21
PCB ordered 11/22
Parts in after thanksgiving break 
Assembled before 12/20


## Useful Links

M95Pxx https://www.st.com/resource/en/datasheet/m95p32-i.pdf

