
# x86 Kernel in C

## Overview

I implemented an **advanced x86 kernel in C** with low-level hardware interaction and direct memory management, running without an underlying operating system. This project demonstrates core operating system concepts including bootstrapping, interrupt handling, and kernel-level execution in protected mode.

## Features

* **Bare-metal Execution**
  Runs directly on hardware without any OS support

* **Boot Integration**
  Loaded via a custom bootloader and executes at a low memory address

* **Kernel Initialization**
  Sets up essential structures required for kernel execution

* **Interrupt Handling (Basic)**
  Supports basic interrupt-driven functionality (if implemented)

* **Screen Output (VGA Text Mode)**
  Prints output directly to video memory (`0xB8000`)

* **Memory Handling**
  Demonstrates low-level memory access and control

## How It Works

1. System boots via BIOS and loads the bootloader
2. Bootloader loads the kernel into memory
3. Kernel starts execution in x86 mode
4. Initializes hardware-level components
5. Writes output directly to the screen

## Technologies Used

* C (freestanding environment)
* x86 Assembly (for bootstrapping)
* GCC cross-compiler (e.g., `i686-elf-gcc`)
* NASM (for assembly parts)

## Build & Run

### Build

```bash id="3kbr1o"
make
```

### Run (QEMU)

```bash id="8kkc7c"
qemu-system-x86_64 -kernel kernel.bin
```

---

## Project Structure

```id="1x4b6k"
.
├── boot/        # Bootloader (assembly)
├── kernel/      # Kernel source code (C)
├── include/     # Header files
├── Makefile
└── README.md
```

---

## Key Concepts Demonstrated

* x86 architecture basics
* Kernel boot process
* Memory-mapped I/O
* Interrupts and low-level control
* Freestanding C environment

---

## Limitations

* Minimal hardware support
* No multitasking
* No memory protection or paging
* No filesystem

---

## Future Improvements

* Implement paging and virtual memory
* Add keyboard drivers
* Introduce process scheduling
* Build a simple shell
* Extend to a multi-stage kernel

---

