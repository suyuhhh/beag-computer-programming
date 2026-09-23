# Beag Computer Programming and Buzzer Peripheral

A Digital Systems coursework project exploring low-level programming and peripheral control using the Beag teaching computer in Logisim-evolution.

The project covers a display output program, a buzzer peripheral extension, and machine-code and ROM data preparation for melody playback.

## My Contribution

The base Beag computer circuit was provided by the lecturer. I independently completed the programming and peripheral extension tasks for Parts A–D, including:

* Programming an asterisk loop for the display.
* Extending the supplied circuit with a buzzer, a 16-bit register, address comparison and control logic.
* Developing the assembly logic for reading note data and writing it to the buzzer address.
* Encoding instructions and note frequencies as hexadecimal ROM contents.
* Documenting the implementation in the project report.

## Technologies and Concepts

* Logisim-evolution
* Beag assembly and 16-bit machine code
* Registers, ROM and RAM
* Memory-mapped I/O
* Address decoding and peripheral control
* Conditional branches and loops

## Project Files

| File                 | Description                                                           |
| -------------------- | --------------------------------------------------------------------- |
| `beag_task_a.circ`   | Display program intended to print five asterisks using a loop.        |
| `beag_task_b.circ`   | Beag circuit extended with a buzzer peripheral and supporting logic.  |
| `beag_task_d.circ`   | Beag circuit containing the melody program and frequency data in ROM. |
| `project_report.pdf` | Explanation of Tasks A–D, implementation decisions and data encoding. |

Part C is described in the report. A separate assembly source file is not included.

## Implementation Overview

### Part A — Display Programming

The program sets up the display address, an asterisk character and a loop counter. Store, subtraction and branch instructions are used to repeat the output five times.

### Part B — Buzzer Peripheral

The circuit adds a buzzer interface using address `0x4003`. A 16-bit register stores the value written by the CPU, with address comparison and control logic supporting peripheral access. A bit-width adapter connects the register output to the buzzer input.

The existing display and keyboard remain in the circuit.

### Parts C and D — Melody Programming and ROM Data

The melody program is designed to read frequency values from ROM and write them to the buzzer address. Its control flow includes note sequencing, a delay loop and a restart condition.

Instructions are stored as hexadecimal machine code alongside the melody data. Rest notes are represented by `0x0000`, intended to produce silence.

## Opening the Project

1. Install Logisim-evolution. The supplied circuit files were saved with version 3.9.0.
2. Download or clone this repository.
3. Open a `.circ` file in Logisim-evolution.
4. Inspect the circuit and ROM contents.
5. Use the simulator's reset and clock controls to step through execution.
6. Refer to the report for the intended behaviour of each task.

These files are simulator projects and do not require physical hardware.

## Current Limitations

This repository preserves the separate coursework task versions.

* The buzzer extension is present in `beag_task_b.circ`, while the melody program is stored in `beag_task_d.circ`.
* The Part D circuit does not yet include the Part B buzzer hardware, so it is not a standalone working melody player.
* The melody program and buzzer circuit need to be integrated and tested together before complete playback can be claimed.
* Complete assembly source files and automated simulation tests are not included.

## Acknowledgements

The Beag base circuit and teaching examples were supplied as course materials. This repository documents my programming work and peripheral extensions built on that foundation.

## Author

Weihao Li
University College Dublin
