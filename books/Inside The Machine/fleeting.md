# Inside The Machine

## Basic Computing Concepts - Chapter 1

`In a nutshell, a computer is a device that reads, modifies, and writes sequences of nkmbers. These three function-read, modify, and write- are the three most fundamental function that a computer performs, and all of the machines components are designed to aid in carrying them out.`

### 3 key components of a computer

- **Storage** (a location where cpu can read and write data)
- **ALU** (performs arithmetic and logic operations)
- **Bus** (carries the data to components)

### Steps on how computer computes an addition

```
1. Load the two operands from main memory into the two source registers.
2. Add the contents of the source registers, and place the results in the destination register, using the ALU.
3. Store the contents of the destination register in main memory.
```

### Register

- A small fixed size storage in the CPU
- Registers in the CPU are group together in a `register file`
- They store operands to be used by the ALU and results computed by the ALU

### RAM

- The dataset is stored mainly in the `main memory`, and only a small portion of the data at a time is moved to the registers for easy access from the ALU.
- Located farther away from the CPU unlike registers
- Connected to the processor via `memory bus`

### A closer look at the code stream

- The code stream are a sequence of operation that will performed by the computer and contains the logic of the executing program
- `General Instruction Type`
  - `Arithmetic`: perform arithmetic operations
  - `Memory Access`: move data from and to main memory (load and store)
  - `Branch`: special type of memory access instruction, but only access code storage not data storage

### A closer look at memory access: Register vs. Immediate

- `immediate`: explicit value in the instruction instead of a memory location
- `register relative addressing`
  - Use the fixed based address in register and add an offset value to locate the actual memory address to operate
  - Allow programmers to write program without knowing the exact location of data in the memory - you only need the base address. E.g., Accessing value of an array
- `absolute addressing`: Explicit address location

### General purpose registers

- They are not fixed to a spearial and fixed role
- Can be used by a wide variety of stask such as: holding operands, storgin intermediate results, acting as counters or temporary varialbles, keeping memory address, and etc.

## The mechanics of Program Execution - Chapter 2
