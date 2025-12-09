# The Elements of Computing System - Review Questions

## Chapter 3 - Sequential Logic & General Concepts

### Knowledge Check:

**1. Sequential vs Combinational Logic:** What are the three key differences between sequential and combinational digital logic circuits?

```
1. Sequential: Memory; Combinational: Gates
2. Sequential: For storing temp data; Combination: Computations
```

**Feedback:** ⚠️ Partially correct but incomplete (missing third difference and some inaccuracies)

**Corrections:**

1. **Memory**: Sequential has memory elements, combinational doesn't ✅
2. **Time awareness**: Sequential is time-dependent, combinational is not
3. **Clock dependency**: Sequential requires clock signals, combinational doesn't

**Note**: Both use gates! Combinational circuits also do computations, but sequential can store results.

**2. Clock Fundamentals:** If a processor runs at 3.2 GHz, what is the period of one clock cycle? Show your calculation.

```
P = 1 / 3.2 * 10^9
P = .03125 * 10^-9
P = .3125 ns

```

**Feedback:** ❌ Calculation error in the formula application

**Correction:**

- T = 1/f where f = 3.2 × 10⁹ Hz
- T = 1/(3.2 × 10⁹) = 0.3125 × 10⁻⁹ = 0.3125 ns

**Your Error**: You wrote `1 / 3.2 * 10^9` instead of `1 / (3.2 × 10^9)`. The parentheses matter!

**3. Flip-Flop Behavior:** Explain why a flip-flop doesn't change its output immediately when the input changes. When does it actually change?

```
Because of the feebback loop where the output is feed back to the input.
```

**Feedback:** ❌ Incorrect reasoning

**Correction:** Flip-flops don't change immediately because they're **synchronized to the clock**. They only update their output on clock edges (rising or falling edge, depending on design).

**Study Note:** Feedback loops enable memory, but clock synchronization controls timing.

**4. Fan-in Rule:** According to your notes on chip design rules, what does "fan-in of 1" mean for internal pins?

```

```

**Feedback:** ❌ No answer provided

**Answer:** Fan-in of 1 means each internal pin must have exactly **one signal source** driving it. This prevents conflicts from multiple drivers trying to control the same pin.

**Study Tip:** Review your chip design rules - this is a fundamental constraint for reliable circuit operation.

**5. Program Counter:** How does a program counter relate to instruction execution in a CPU?

```
The program counter is resposible at pointing to the next instruction to execute by the CPU
```

**Feedback:** ✅ Correct concept!

**Minor Corrections:**

- Spelling: "resposible" → "responsible"
- Grammar: "responsible **for** pointing" not "responsible at pointing"

**Additional Detail:** The PC holds the **address** of the next instruction in memory.

**6. Feedback Loops:** What is a feedback loop in digital circuits, and why might it be important for sequential logic?

```
Feedback loops are mechanism that allows you to feed the output back to the input
```

**Feedback:** ✅ Good definition, but missing the "why" part

**Complete Answer:** Feedback loops create a closed path from output back to input. They're crucial for sequential logic because they enable **memory** - the circuit can "remember" its previous state.

**Key Insight:** Without feedback, circuits can't store information over time.

**7. Word Size:** If a register has a "word size" of 32 bits, what does this tell you about the processor architecture?

```
It tells me that the processor can only process 32 bits or 4 bytes of data at a time, no more than that
```

**Feedback:** ✅ Mostly correct understanding

**Clarification:** The processor **typically** operates on 32-bit chunks most efficiently, but modern processors can often handle multiple words or smaller chunks too.

**Additional Info:** 32-bit word size also affects address space (2³² addressable locations) and instruction encoding.

**8. Negative Numbers:** Using the sign-bit method from your notes, how would you represent -5 in 4-bit binary?

```
For sign-bit method, to identify negative sign is to have the leftmost bit to be 1. In case of -5 its binary form will 1101
```

**Feedback:** ✅ Correct!

**Verification:**

- +5 in binary: 101
- Sign-bit method: 1 (negative) + 101 (magnitude) = 1101
- Perfect!

**Note:** This differs from two's complement representation (which would be 1011 for -5).

---

## Overall Assessment:

- **Strengths:** Program counter concept, word size understanding, sign-bit binary representation
- **Areas to improve:** Clock period calculations (parentheses in formulas), flip-flop timing behavior
- **Missing knowledge:** Fan-in rules - review your chip design notes!
- **Next steps:** Practice timing calculations and study clock synchronization concepts

_Test your understanding of digital logic fundamentals and sequential circuits._
