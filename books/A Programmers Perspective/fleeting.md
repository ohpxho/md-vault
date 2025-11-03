# A Programmer's Perspective

## Chapter 1 - A Tour of Computer System

```
A system is more than just hardware. It is a collection of intertwined hardware and systems software that must cooperate in order to achieve the ultimate goal of running application programs.
```

- All information in the system are represented as a bunch of bits.
- Because of physical laws, larger storage device are slower than smaller storage device

### Translation of source code to executable

- 4 phases: preprocessing, compilation, assembling, linking
- `Preprocessing`: insert content from header files; another c file with .i extension
- `Compilation`: translate into assembly with .s extension
- `Assembly`: translate into machine language, package them in a form known as `relocatable object program`, and stores the result into an object file with .o extension.
- `Linking`: link or merge related object file which result into an exe file, ready to be executed.

### Hardware Organization of a System

- `Buses`
  - Carries data among components
  - Amount of data is limited to the word size of the computer e.g. 32-bit pc: 4 bytes, 64-bit pc: 8 bytes
- `I/O Devices`
  - A keyboard or mouse
  - External device connected via I/O bus by a controller or adapter
- `Main Memory`
  - A temporary storage device that holds the data and the program
  - Physically, a collection of DRAM(dynamic random access memory) chips
  - Memory is organized as a linear array of bytes starting at 0
- `Processor`
  - execute the instruction in main memory
  - `register file`: a small storage device consist of word-size lenght registers each with unique names.
  - `register`: a word-size and quick access temporary storage
  - `program counter`: points to the next instruction, a special register, increments sequentially
  - `arithmetic logic unit`: computes new data and address values
  - CPU operations:
    - **Load**: copy a byte from main memory into the register overwriting it
    - **Store**: copy a byte from the register to the main memory overwriting it
    - **Operate**: copy contents from register into ALU for processing, then store it into a register overwriting it
    - **Jump**: if the current instruction os a jump/branch, the CPU overwrites the value of the PC with the target address specified

### What are cache memories?

- Temporary staging areas for information that the processor will need in the future
- Cache levels:
  - `L1` - 10k bytes, as fast as registers
  - `L2` - 1M bytes, 5x slower than L1
  - `L3` - bigger, slower, **shared across cores**
- Implemented using SRAM(static random memory access)

### Memory Hierarchy

```
        +-----------+
        | L0 Regs   |
        +-----------+
        | L1 Cache  |
        |  (SRAM)   |
        +-----------+
        | L2 Cache  |
        |  (SRAM)   |
        +-----------+
        | L3 Cache  |
        |  (SRAM)   |
        +-----------+
        | L4 Memory |
        |  (DRAM)   |
        +-----------+
        | L5 Local  |
        |  Disks    |
        +-----------+
        | L6 Remote |
        |  Storage  |
        +-----------+

 ↑ Faster, smaller, costly
 ↓ Slower, larger, cheap

```

- The storage at one level serves as a cache of the storage in the lower level e.g. Reg -> L1, L1 -> L2..

### Role of operating system

- Runs in between applications and hardware
- Provide application with mechanisms to interact with the hardware
- Protect the hardware from misuse
- All try of the application to manipulate the hardware must go through the operating system

### Process in OS

- An abstraction of OS for a running program
- `context` - states of the process which includes: current value of the PC, register file, contents of the main memory, and etc.
- Each process has an exclusive use of the hardware
- `context switch` - a process where OS stops the current process and runs another one saving its states and load the new state to run

### Thread

- An execution unit in a process
- Threads in a process share same data (heap, global var, codem etc.) in the memory, but has different execution path (pc, stack, registers)

### Virtual Memory

- Abstraction of OS to main memory
- Each process has its own virtual memory space
- Areas:
  - `Program code and data`
  - `Heap`: expands and contracts dynamically
  - `Shared libraries`: Near the middle of the address space area, holds the data and code for shared libraries such as the C stdlib
  - `Stack`: At the top of the virtual space after kernel; Each function call the stack will group, and each time it return it contracts
  - `Kernel virtual memory`: Sits at the top of the virtual space

### Amdahl's law

- An estimate that computes how much the system performance will improve if you optimize a specific part of it.

```
S(N) = 1 / ((1-P) + P/N)

S(N) = speedup with N processors
P = proportion of the program that can be parallelized
1 - P = Propportion that must remain serial(sequential)
N = Number of processors
```

- **Insight:** The speedup even with infinite processors are limited to the speed of the sequential portion

### Concurrency and Parallelism

## Chapter 2 - Representing and Manipulating Information
