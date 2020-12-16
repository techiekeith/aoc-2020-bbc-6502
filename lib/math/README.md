# Math library

**This library is deprecated; use aoclib instead**

A simple library for doing unsigned integer arithmetic, for integers between 1 and 8 bytes (8 to 64 bits) wide.

## Getting started

* Launch BeebEm
* In BeebEm menu bar, select `File` **>** `Load Disc 0...`
* Select the disk image `diskimage.ssd`, then select `Open`

## Loading the library from disk

```
*LIB L
*MATH
```
This loads the math library into memory at location &7800.

## Important addresses

### Zero page

Locations &8C-&8F are used by various math functions. Do not store anything in these locations that you want to keep.

### Function calls

- &7800 - Set Integer Width (A contains the number of bytes per integer, 1 <= A <= 8)
- &7803 - Add
- &7806 - Subtract
- &7809 - Multiply
- &780C - Divide
- &780F - Display zero terminated string starting from byte following call instruction (do not call this from BASIC!)
- &7812 - Display number in decimal. X and Y contain a pointer to the number to display (X = LSB, Y = MSB)
- &7815 - Display number in hexadecimal. X and Y contain a pointer to the number to display (X = LSB, Y = MSB)
- &7818 - Display 16-bit number in hexadecimal. X and Y contain the number to display (X = LSB, Y = MSB)
- &781B - Display 8-bit number in hexadecimal. A contains the number to display

### Variables

- &781E - Counter 1 (Multiply, Divide)
- &781F - Counter 2 (Display Decimal)
- &7820 - First Operand (Add, Subtract, Multiply); Dividend (Divide)
- &7828 - Second Operand (Add, Subtract, Multiply); Divisor (Divide)
- &7830 - Result (Add, Subtract, Multiply); Quotient (Divide)
- &7838 - Remainder (Divide)
- &7840 - Temporary number (Multiply, Divide)
- &7848 - Integer width (Set Integer Width)
- &7849 - Display buffer (Display Decimal)
- &785E - Display buffer width lookup table (Display Decimal)

## Updating the library

### Disable disk write protection

* Select `File` **>** `Disc Options` **>** `Write Protect 0`

### Build

* Load `math.6502` into a text editor
* Copy the contents to the clipboard
* In BeebEm menu bar, select `Edit` **>** `Paste`
* Press the **Esc** key
* Enter `RUN`

### Run tests

* Enter `PROCtest`

### Save to disk

* Enter `RUN`
* Enter `PROCsave`
