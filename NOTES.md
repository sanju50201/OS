# Introduction to the x86 architecture and the OS we're building

- x86 is the most common instruction set architecture (ISA) in use today, most OS's or softwares function with the x86-based hardware

## Specifications:

1. x86-32bit architecture
2. C++
3. Boot with Grub
4. UNIX style
5. Multitasking
6. Modular systems (drivers, filesystems, etc)
7. Modules:
   - IDE disks
   - DOS disks
   - Clock
   - EXT2 filesystem(read-only)
   - Bochs VBE
8. Userland shell:
   - API posix-like
   - LibC
   - Can run shell

## Development environment:

- Vagrant: helping us to create a clean virtual development environment
- VirtualBox: virtual machine, vagrant needs virtual box to run

## How the Computer Starts:

1. BIOS is copied from a ROM chip to RAM
2. BIOS starts executing code
   - intializes hardware
   - runs some tests (POST = power-on-self test)
3. BIOS searches for an operating system to start
4. BIOS loads and starts the operating system
5. Operating System runs

## How the BIOS finds the OS:

- **Legacy Booting**:

  - BIOS loads the first sector of each bootable device into memory (at location 0x7c00)
  - BIOS checks for 0xaa55 signature
  - if found, it starts executing the code

- **EFI**:

  - BIOS looks into specific EFI partitions
  - Operating system must be compiled as an EFI program
