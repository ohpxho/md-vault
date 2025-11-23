# Computer Architecture Notes - Nov. 22, 2025

## Memory

### Heap Fragmentation

- A case where the heap's memory is fragmented or not contiguous
- There are multiple gaps in the memory and the heap can't be used as efficiently

Sources: https://www.youtube.com/watch?v=ioJkA7Mw2-U

### Stack

- A stack is part of memory where function calls, local variables, save registers, and return addresses are stored
- It grows downwards (toward lower memory addresses):
  - pushing -> decreases the stack pointer
  - popping -> increases the stack pointer
- The stack pointer points to the top of the stack

### Why Stack grows downwards while heap grows upwards?

- A simple answer is that, so they don't collide with each other

### Memory Layout

- The layout of memory in a process is consist of:
  1. Text segment
  - Executable code
  - Read-only
  - Size depends on the number of instructions and the program's complexity
  2. Data segment (Data)
  3. Stack segment
  4. Heap segment
  5. BSS segment
