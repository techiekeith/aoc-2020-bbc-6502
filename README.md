# aoc-2020-bbc-6502
An attempt to do at least some of [Advent of Code 2020](https://adventofcode.com/) in 6502 assembly language on a BBC Micro (or BeebEm emulator).

Tools used:

* [BeebEm for Windows](https://github.com/stardot/beebem-windows)
* The [BBC Microcomputer Advanced User Guide](http://stardot.org.uk/mirrors/www.bbcdocs.com/filebase/essentials/BBC%20Microcomputer%20Advanced%20User%20Guide.pdf)
* [Visual Studio Code](https://code.visualstudio.com/), [Notepad++](https://notepad-plus-plus.org/) (any IDE or text editor will do)

## How to run

### Before you start

* Launch BeebEm
* In BeebEm menu bar, select `File` **>** `Load Disc 0...`
* Select the relevant disk image, then select `Open`
    * Days 1-10: `disc1.ssd`
    * Days 11+: `disc2.ssd`

### From disk image

* Enter `*DAYnn`

### From source

* Load the file containing the assembly source code (e.g. `day1.6502`) into a text editor
* Copy the contents to the clipboard
* In BeebEm menu bar, select `Edit` **>** `Paste`
* Press the **Esc** key
* Enter `RUN` to assemble the program
* Enter `PROCtest` to run the program against the test data
* Enter `CALL run` to run the program against the real data
* Enter `PROCsave` to save the program to the disk image

## Data files associated with these programs

The text files needed to run these programs are available from [my main Advent of Code 2020 GitHub repository](https://github.com/techiekeith/advent-of-code-2020). File mappings are as follows:

* `data/day/n/input.txt` **->** `A.DAYnn`
* `data/day/n/test.txt` **->** `T.DAYnn`

## Goals

* Complete more days of AoC 2020
* Hook up a real BBC Micro so I can run these solutions natively
