# aoc-2020-bbc-6502
An attempt to do at least some of Advent of Code 2020 in 6502 assembly language on a BBC Micro (or BeebEm emulator).

Tools used:

* [BeebEm for Windows](https://github.com/stardot/beebem-windows)
* The [BBC Microcomputer Advanced User Guide](http://stardot.org.uk/mirrors/www.bbcdocs.com/filebase/essentials/BBC%20Microcomputer%20Advanced%20User%20Guide.pdf)
* [Visual Studio Code](https://code.visualstudio.com/), [Notepad++](https://notepad-plus-plus.org/) (any IDE or text editor will do)

## How to run

### Before you start

* Launch BeebEm
* In BeebEm menu bar, select `File` **>** `Load Disc 0...`
* Select the disk image `diskimage.ssd`, then select `Open`

### From disk image

* Enter `CHAIN "DAY`*NN*`"` (where *NN* is between 01 and 25) to assemble the program and run against the test data
* Enter `$filename="A.DAY`*NN*`":CALL start` to run the assembled program against the real data

### From source

* Load the file containing the assembly source code (e.g. `aoc-day1.6502`) into a text editor
* Copy the contents to the clipboard
* In BeebEm menu bar, select `Edit` **>** `Paste`
* Press the **Esc** key
* Enter `RUN` to assemble the program and run against the test data
* Enter `$filename="A.DAY`*NN*`":CALL start` to run the assembled program against the real data

## Data files associated with these programs

The text files needed to run these programs are available from [my main Advent of Code 2020 GitHub repository](https://github.com/techiekeith/advent-of-code-2020). File mappings are as follows:

* `data/day/`*N*`/input.txt` **->** `A.DAY`*NN*
* `data/day/`*N*`/test.txt` **->** `T.DAY`*NN*

## Goals

* Complete more days of AoC 2020
* Hook up a real BBC Micro so I can run these solutions natively
