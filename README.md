# RISC-V ucore Operating System Labs

Operating systems course project built on the RISC-V ucore teaching framework, with hands-on work in virtual memory, page replacement, process management, traps, and kernel debugging.

**Tech Stack:** C · RISC-V · ucore · QEMU · GDB

**Highlights**
- Implemented an LRU page replacement module with page-access tracking and victim selection.
- Implemented process-control-block initialization in `alloc_proc` and breakpoint exception handling.
- Used QEMU/GDB and custom tests to inspect and validate kernel behavior.

This repository is a cleaned public mirror for portfolio and resume review. It preserves the team-project nature of the coursework and does not present the work as an operating system built from scratch.

## Framework

- **Base system:** RISC-V ucore teaching framework
- **Language:** C with RISC-V-specific kernel support code
- **Execution and debugging:** QEMU, GDB, ucore grading scripts
- **Core topics:** traps and exceptions, page tables, page faults, swap, process control blocks, context switching, scheduling, system calls, and memory allocators

## My Contributions

- Implemented a Lab 3 LRU page replacement module by adding a swap manager, tracking page access counts, checking RISC-V page-table Accessed bits, selecting swap victims, and validating behavior with custom page-access tests.
- Implemented Lab 4 process control block initialization in `alloc_proc`, setting process state, PID, page table base, kernel stack metadata, scheduling fields, trapframe pointer, saved context, and process name storage.
- Implemented Lab 1 breakpoint exception handling and used QEMU/GDB-based workflows to inspect and validate kernel behavior.
- Added page-level access-count metadata to support the LRU policy and documented virtual-memory and process-management behavior in lab reports.

## Selected Files

- `riscv64-ucore-labcodes/lab3/kern/mm/swap_lru.c`: LRU page replacement implementation.
- `riscv64-ucore-labcodes/lab3/kern/mm/swap_lru.h`: LRU swap manager interface.
- `riscv64-ucore-labcodes/lab3/kern/mm/memlayout.h`: Page metadata extension for access counting.
- `riscv64-ucore-labcodes/lab4/kern/process/proc.c`: Process control block initialization.
- `riscv64-ucore-labcodes/lab1/kern/trap/trap.c`: Breakpoint exception handling.

## Major Lab Areas

- **Lab 1:** RISC-V boot flow, trap handling, timer interrupts, exception handling, and QEMU/GDB debugging.
- **Lab 2:** Physical memory management and allocator design.
- **Lab 3:** Virtual memory, page tables, page fault handling, FIFO/Clock/LRU page replacement, and swap manager interfaces.
- **Lab 4:** Process control blocks, kernel threads, process creation flow, kernel stacks, trapframes, saved context, and process switching.
- **Later labs:** User process loading, fork/exec/wait/exit flow, system calls, scheduling extensions, and Copy-on-Write.

## Team Scope

Other team members implemented or extended additional kernel components, including memory allocators, Clock page replacement, `do_pgfault`, `proc_run`, `do_fork`, system-call paths, scheduling-related code, and Copy-on-Write. These are part of the team project scope, not claims of sole implementation.

## Notes

Generated build artifacts, disk images, object files, and local debugging outputs are intentionally excluded from this cleaned mirror.
