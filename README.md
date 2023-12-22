# UART Kernel Module Development

## Overview
This repository contains the development files for a UART kernel module named `uart.ko`. This module is designed as a character device driver in Linux, with functionalities determined by passed parameters. It focuses on handling UART communication, specifically for COM1 and COM2 ports.

## Features
- Implemented as a kernel module `uart.ko`.
- Accessed as a character device driver.
- Configurable via module parameters:
  - `major`: Specifies the major number for device registration.
  - `option`: Determines the operational mode (`OPTION_BOTH`, `OPTION_COM1`, `OPTION_COM2`).
- Default values are `major=42` and `option=OPTION_BOTH`.
- Handles interrupts for COM1 (IRQ 4) and COM2 (IRQ 3).
- Utilizes `kfifo` for read/write buffers.
- Synchronization with wait queues for blocking read/write operations.

## Kernel Module Details
- **Source Files**:
  - `uart.c`: Main module source code.
  - `uart.h`: Header file with necessary definitions and declarations.
- **Makefile**: For compiling the kernel module.

## Loading the Module
- **Load Script**: `load_module.sh` to insert the module with specific parameters.
- Parameters can be passed to the script, e.g., `sudo ./load_module.sh 42 OPTION_BOTH`.

## Testing
- Automated testing with `_checker` script.
- Ensure default serial drivers are disabled to avoid conflicts.

## Building and Running
- Compile the module using the provided Makefile.
- Load the module using `sudo insmod uart.ko major=XX option=YYY`.
- Test the functionality with `_checker` and custom test scripts.

## Contributions
- Contributions and improvements are welcome, particularly in optimization and extended functionality.
- For major changes, open an issue first to discuss proposed changes.

## Contact
- **Name**: Cade
- **Institution**: University of Denver
- **Field of Study**: Computer Engineering

Feel free to reach out for any discussions, queries, or collaborations related to this UART kernel driver development project.

---

This README will be updated periodically to reflect the latest progress and developments in the `uart.ko` kernel module.
