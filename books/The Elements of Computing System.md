# The Elements of Computing System

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
- A device that generates oscillating signal(continuous alternating signal without need of inputs)
- The elapsed time from high to low signal is a cycle.
- The alternating signal is represented by the computer as binary: 1 or 0
- The signal is simultaneously broadcast to every sequential chip

### What is a flip-flop
- The most elementary sequential element

## Others 

### Two types of digital logic
- Combinational 
- Sequential

### How are negative numbers represented in binary? 
- One way is to define it by making the leading 0 into 1
```
0001 = 1
1001 = -1
```
