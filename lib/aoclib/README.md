# Advent of Code library

A library containing various tools, including:

* arithmetic for unsigned integers up to 64 bits wide
* reading files
* displaying decimal and hexadecimal numbers
* parsing integers in strings
* program timing
* displaying results

## Getting started

* Launch BeebEm
* In BeebEm menu bar, select `File` **>** `Load Disc 0...`
* Select the disk image `diskimage.ssd`, then select `Open`

## Loading the library from disk

```
*LIB L
*AOCLIB
```
This loads the library into memory at location &7600.

## Important addresses

### Zero page

Locations &8A-&8F are used by various functions. Do not store anything in these locations that you want to keep.

### Main RAM area

Locations &7500-75FF are used as a buffer for reading files.

Locations &7600-7BFF are reserved for the library.

### Function calls

- &7600 - Set Integer Width (A contains the number of bytes per integer, 1 <= A <= 8)
- &7603 - Add first and second operands, store result in Result
- &7606 - Subtract second operand from first, store result in Result
- &7609 - Multiply first and second operands, store result in Result
- &760C - Divide first operand by second, store quotient in Result/Quotient, remainder in Remainder
- &760F - Display zero terminated string following instruction (do not call from BASIC)
- &7612 - Display number in decimal. X and Y contain a pointer to the number to display (X = LSB, Y = MSB)
- &7615 - Display number in hexadecimal. X and Y contain a pointer to the number to display (X = LSB, Y = MSB)
- &7618 - Display 16-bit number in hexadecimal. X and Y contain the number to display (X = LSB, Y = MSB)
- &761B - Display 8-bit number in hexadecimal. A contains the number to display
- &761E - Copy number from operand or variable to destination (A = variable number, X = LSB, Y = MSB)
- &7621 - Copy number to operand or variable from source (A = variable number, X = LSB, Y = MSB)
- &7624 - Open input file (A = day number, C set if using test input file)
- &7627 - Close currently open input file
- &762A - Read line to buffer (X = LSB, Y = MSB)
- &762D - Read record to buffer (X = LSB, Y = MSB); a blank line is considered to be the end of a record
- &7630 - Parse integer at pointer (X = LSB, Y = MSB)
- &7633 - Initialise the library
- &7636 - Display results contained in Part 1 results and Part 2 results variables
- &7639 - Display zero terminated string at pointer (X = LSB, Y = MSB)
- &763C - Display tick
- &763F - Set operand or variable value to zero (A = variable number)
- &7642 - Determines whether the Result is zero or negative
- &7645 - Reserved for future use

### Variables

Memory addresses of important variables are shown below. The number in parentheses after the address is the variable number for use with the copy and zero operand commands.

- &766E - Counter 1 (Multiply, Divide)
- &766F - Counter 2 (Display Decimal)
- &7670 (#0) - First Operand (Add, Subtract, Multiply); Dividend (Divide)
- &7678 (#1) - Second Operand (Add, Subtract, Multiply); Divisor (Divide)
- &7680 (#2) - Result (Add, Subtract, Multiply); Quotient (Divide)
- &7688 (#3) - Remainder (Divide)
- &7690 (#4) - Temporary number (Multiply, Divide)
- &7698 (#5) - Elapsed time (ms, to nearest 1/100 sec.)
- &76A0 (#6) - Program start time (system clock, 1/100 sec.)
- &76A8 (#7) - Program stop time (system clock, 1/100 sec.)
- &76B0 (#8) - Part 1 results
- &76B8 (#9) - Part 2 results
- &76C0 - Display buffer (Display Decimal)
- &76D6 - File handle
- &76D7 - Integer width (Set Integer Width)
- &76D8 - Tick colour
- &76D9 - Tick counter
- &76DA - Table containing maximum number of ASCII digits for differently sized integers (Display Decimal)
- &76E2 - Tick block graphics
- &76E8 - Input filename

## Updating the library

### Disable disk write protection

* Select `File` **>** `Disc Options` **>** `Write Protect 0`

### Build

* Load `aoclib.6502` into a text editor
* Copy the contents to the clipboard
* In BeebEm menu bar, select `Edit` **>** `Paste`
* Press the **Esc** key
* Enter `RUN`

### Run tests

* Enter `PROCtest`

### Save to disk

* Enter `RUN`
* Enter `PROCsave`
