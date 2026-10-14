# Lab DA-5: Virtual Memory and Page-Table Mapping in xv6

**VTOP Lab DA-7,8**

## Objective
To understand virtual memory and page-table mapping in xv6 by inspecting virtual-to-physical address translation and observing process memory isolation after `fork()`.

## Implementation
- Examined page-table operations in `vm.c`, including `walkpgdir()`, `mappages()`, and `copyuvm()`.
- Added the `vmdebug()` system call to inspect virtual memory mappings.
- Displayed virtual addresses, physical page addresses, page offsets, and page-table flags.
- Created `vmtest.c` to examine global, local, and heap variables before and after `fork()`.
- Verified that modifications made by the child process do not change the parent's values.

## Files
- `vm.c` — Virtual-memory functions and `sys_vmdebug()`.
- `vmtest.c` — Test program for memory mappings and process isolation.
- `syscall.h`, `syscall.c`, `sysproc.c`, `defs.h`, `user.h`, `usys.S` — System-call declarations and integration.
- `Makefile` — Build configuration.
- `main.c` — xv6 initialization source included with this implementation.

## Expected Result
The test program prints virtual addresses, physical page bases, offsets, and mapping flags for selected variables. After `fork()`, the child modifies its values, while the parent's original values remain unchanged.

## Platform
- xv6-public (x86)
- C
- QEMU
