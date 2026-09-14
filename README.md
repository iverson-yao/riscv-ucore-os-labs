# RISC-V ucore Operating System Labs

Team-based operating systems course project built on the RISC-V ucore framework. The project implemented and extended selected kernel components across multiple labs, including trap handling, physical memory management, virtual memory, page replacement, process management, scheduling, system calls, and Copy-on-Write.

This repository is a cleaned public mirror for portfolio and resume review. It preserves the team-project nature of the coursework and does not present the work as an operating system built from scratch.

## Framework

- Base system: RISC-V ucore teaching framework
- Language: C with RISC-V-specific kernel support code
- Execution and debugging: QEMU, GDB, ucore grading scripts
- Core topics: traps and exceptions, page tables, page faults, swap, process control blocks, context switching, scheduling, system calls, and memory allocators

## Major Lab Areas

- Lab 1: RISC-V boot flow, trap handling, timer interrupts, exception handling, and QEMU/GDB debugging.
- Lab 2: Physical memory management, Best-Fit allocator, Buddy allocator, SLUB allocator discussion, and physical memory range analysis.
- Lab 3: Virtual memory, page tables, page fault handling, FIFO/Clock/LRU page replacement, swap manager interfaces, and page replacement testing.
- Lab 4: Process control blocks, kernel threads, process creation flow, kernel stacks, trapframes, saved context, and process switching.
- Lab 5 and later: User process loading, fork/exec/wait/exit flow, system calls, scheduling extensions, and Copy-on-Write.

## My Verified Contributions

The team divided work by lab exercises and challenges. My personally attributable contributions in the public repository include:

- Implemented a Lab 3 LRU page replacement module by adding a swap manager, tracking page access counts, checking RISC-V page-table Accessed bits, selecting swap victims, and validating behavior with custom page-access tests.
- Added page-level access-count metadata to support the LRU replacement policy.
- Implemented Lab 4 process control block initialization in `alloc_proc`, setting process state, PID, page table base, kernel stack metadata, scheduling fields, trapframe pointer, saved context, and process name storage.
- Implemented Lab 1 breakpoint exception handling and used QEMU/GDB-based workflows to inspect and validate kernel behavior.
- Wrote lab reports explaining virtual-memory behavior, page replacement design, process metadata, and debugging results.

## Team Contributions

Other team members implemented or extended additional kernel components, including Best-Fit and Buddy memory allocators, Clock page replacement, `do_pgfault`, `proc_run`, `do_fork`, system-call paths, scheduling-related code, and Copy-on-Write. Those are described here as team project scope, not as my sole implementation.

## Selected Files

- `riscv64-ucore-labcodes/lab3/kern/mm/swap_lru.c`: LRU page replacement implementation.
- `riscv64-ucore-labcodes/lab3/kern/mm/swap_lru.h`: LRU swap manager interface.
- `riscv64-ucore-labcodes/lab3/kern/mm/memlayout.h`: Page metadata extension for access counting.
- `riscv64-ucore-labcodes/lab4/kern/process/proc.c`: Process control block initialization.
- `riscv64-ucore-labcodes/lab1/kern/trap/trap.c`: Breakpoint exception handling.

## Notes

Generated build artifacts, disk images, object files, and local debugging outputs are intentionally excluded from this cleaned mirror. The original course repository included compiled outputs from local ucore/QEMU runs.
