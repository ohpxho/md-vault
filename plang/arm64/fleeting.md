# ARM64 Notes - Oct 19, 2025

- ARM stands for **Advanced RISC Machine**\
- A RISC (Reduced Instruction Set Computer) - uses small, simple, and consistent set of instructions that are fast to execute
- **ARM64** CPUs are used in Apple Silicon(M1, M2, M3), modern Android phones, Raspberry Pi4+, and servers

## Registers

- Has 31 general-purpose 64-bit registers: x0-x30 (each can store 64 bits = 8 bytes)
- `xzr` The zero register (always reads as 0)
- `sp` The stack pointer (points to top of stack)
- `pc` The program counter (points to the next instruction, automatically increments after each instruction)
- `x30` The link register (stores the return address when calling a function)

| Register | Role                                                            | Notes                                             |
| -------- | --------------------------------------------------------------- | ------------------------------------------------- |
| x0-x7    | Function arguments and return values                            | Used to pass parameters between functions         |
| x8       | Indirect result location register / System call number register | Used for special cases                            |
| x9-x15   | Temporary (caller-saved)                                        | Can be freely used in short calculations          |
| x19-x28  | Calle-saved                                                     | Must be preserved accross function calls          |
| x29      | Frame pointer                                                   | Points to the base of the current stack frame     |
| x30      | Link register                                                   | Stores the return address when calling a function |
| x31      | Stack pointer                                                   | Points to the top of the stack                    |
| pc       | Program counter                                                 | Points to the next instruction to be executed     |
| sp       | Stack pointer                                                   | Points to the top of the stack                    |
