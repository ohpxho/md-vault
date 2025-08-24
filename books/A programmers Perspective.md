# A Programmer's Perspective

## Chapter 1 - A Tour of Computer System

- All information in the system are represented as a bunch of bits.

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
