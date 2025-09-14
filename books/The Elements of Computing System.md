# The Elements of Computing System

## Rule in Chip Design
- Internal pins must have a fan-in of 1 (single source)

## Chapter 3 - Sequential Logic

### What is a sequential logic
- A digital logic with memory elements — can store values
- Implementation involves:
    - synchronization
    - clocking
    - feedback loops
- implementation needs a clock signal (in synchronous design)

```
The act of remembering something is inherently time-dependent
```

### What is a clock?
- The passage of time is represented by clock
- A device that generates oscillating signal(continuous alternating signal without need of inputs)
- Generate a fixed-length pulse at fixed intervals
- The elapsed time from high to low signal is a cycle.
- The alternating signal is represented by the computer as binary: 1 or 0
- The signal is simultaneously broadcast to every sequential chip
- measured by hz(hertz) e.g 2ghz => 2 billion pulse per second

### What is a flip-flop
- The most elementary sequential element
- It stores 1 bit of data
- Changes of value will only apply at the clock edge (rising  or falling, depends on the design), it will not change immediately
- The value it has will persist until ca new value os explicitly loaded on a clock edge

### What are counters
- A sequntial chip whose state is an integer number that increments every time unit
- Typical CPU include `program counter` whose output is interpreted as the address of the instruction that should be executed next 

### Feedback loops
- This is a close path in a circuit that feeds the output back to the input

### Difference between open and close path circuits
- **Open path**:  has a break or interruption to prevent the flow of elctricity
- **Close path**: continuous, without break or interruption 

## Others 

### Two types of digital logic
- Combinational (input based, no memory, no time awareness)  
- Sequential (has memory, time aware) 

### How are negative numbers represented in binary? 
- One way is to define it by making the leading 0 into 1
```
0001 = 1
1001 = -1
```

`The basic design parameter of such register is its width - the number of bits that it holds - e.g., 16,32, or 64`

- `word` = width of the registers
