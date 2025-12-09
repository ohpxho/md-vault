# A Programmer's Perspective - Review Questions

## Chapter 1 - A Tour of Computer System

### Quick Understanding Check:

**1. Compilation Pipeline:** Can you explain what happens to a C source file during the preprocessing phase, and what file extension does it get?

```
The compiler will convert all include header files into an actual code, and change the extension of the source file into .i
```

**Feedback:** ✅ Correct! Good understanding. The preprocessor expands `#include` directives by inserting header file contents and produces a `.i` file.

**Additional Notes:** The preprocessor also handles other directives like `#define` macros and conditional compilation (`#ifdef`, `#ifndef`).

**2. Memory Hierarchy:** According to your notes, why is L3 cache special compared to L1 and L2?

```
L3 cache is special because it is shared between cores.
```

**Feedback:** ✅ Excellent! You identified the key distinction.

**Additional Notes:** This sharing allows cores to communicate through the cache and reduces memory duplication, but also means contention between cores can affect performance.

**3. CPU Operations:** What's the difference between a "Load" and "Store" operation in terms of data movement?

```
Load: reads a data
Store: write a data
```

**Feedback:** ✅ Correct concept, but could be more precise.

**Correction:**

- **Load**: Copies data FROM memory TO register
- **Store**: Copies data FROM register TO memory

**Study Suggestion:** Remember the direction of data flow - your notes specify "overwriting" which is important for understanding these operations.

**4. Amdahl's Law:** If 80% of a program can be parallelized and you have 4 processors, what's the theoretical speedup using the formula in your notes?

```
S(N) = 1 / (1-P) + P/N

s(4) = 1 / (1-0.8) + 0.8/4
s(4) = 5.2

The speedup will increase 5.2 times
```

**Feedback:** ❌ Formula error! Check your notes again.

**Correction:** The correct formula is: `S(N) = 1 / ((1-P) + P/N)`

Correct calculation:

- S(4) = 1 / ((1-0.8) + 0.8/4)
- S(4) = 1 / (0.2 + 0.2) = 1/0.4 = 2.5x speedup

**Study Tip:** The denominator should be in parentheses - it represents the total time (serial + parallel portions).

**5. Process vs Thread:** Based on your notes, what's the key difference between processes and threads in terms of memory sharing?

```
Processes are running instance of an application, while threads are execution units of a process. Process can have multiple thread, but there is only one
process. In terms of memory sharing, Processes has its own memory block and it cannot access data outside of its block while multiple running threads in a process shares the same memory block (of its process)
```

**Feedback:** ✅ Good understanding! You got the core concept right.

**Minor Corrections:**

- Typo: ":w" should be removed
- Clarification: Each process has its own virtual memory space (not just "memory block")

**Additional Notes:** Threads share heap, global variables, and code but have separate stacks, registers, and program counters.

**6. Virtual Memory Layout:** Your notes mention the stack "contracts" when a function returns - can you explain why this happens?

```
The stack contracts because it will release the memory assigned to the function returned

```

**Feedback:** ✅ Correct concept, but could be more detailed.

**Expanded Explanation:** When a function returns, its stack frame (containing local variables, parameters, return address) is popped off the stack. The stack pointer moves back to the previous position, effectively "releasing" that memory space for future function calls.

**Study Suggestion:** Review stack frames and how function calls use the LIFO (Last In, First Out) principle.

---

## Overall Assessment:

- **Strengths:** Good grasp of basic concepts, memory hierarchy, and process/thread differences
- **Areas to improve:** Mathematical formulas (Amdahl's Law), precision in technical descriptions
- **Next steps:** Practice more calculations with Amdahl's Law and dive deeper into memory management concepts
