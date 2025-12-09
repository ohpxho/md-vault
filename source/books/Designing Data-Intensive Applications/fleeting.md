# DIA Notes - Dec 08, 2025

## Reliable, Scalable, and Maintanable Applications - Chapter 1

### Reliability

- The ability of the system to continue and work correctly even when a fault occurs.
- Keep on exercising fault finding and testing to fault-tolerant systems. Find faults delibarately and resolve them.

**Kinds of faults:**

1. Hardware Faults

- Refers to fault in hardware components such as: hard disk crash, RAM becomes faulty, the power grid has blackout, etc.
- Redundancy can help when a fault in hardware appears - when one hardware fails there are others to take its place (this cannot prevent hardware from causing failures, they serve as a back up when one fails)

2. Software Errors

- A bug, error, slow performance, etc. in the system layer that causes the applicaton to crash or run unexcpted output.

3. Human Errors

`Humans are known to be unreliable`

```
A study of large internet services found that configuration errors by operators were the leading cause of outages, whereas hardware faults (servers or network) played a role in only 10-25% of outages.
```

**How to make the system reliable, in spite of unreliable humans:**

1. Design systems in a way that minimizes oppurtunities for error
2. Decouple the places where people make the most mistakes from the places where they can cause failures (sandbox environments for exploration and experiments)
3. Test throughly at all levels (unit tests to whole-system integration test and manual test)
4. Allow quick and easy recovery from human errors (quick and effective roolback strategies once mistake is done)
5. Setup detailed and clear monitoring (monitor performance metrics and error rates)
6. Implement good management practices and training

### Scalability

- Strategies that improve or maintain the performance even when load incrreases.

1. Describing Load
2. Describing Performance

## **Approaches for Coping with Load**

### Maintainability

- Writing readable code for ease of understanding of other enginners.

1. Operability
2. Simplicity
3. Evolvability
