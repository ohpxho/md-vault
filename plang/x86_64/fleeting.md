# x86_64 Notes - Aug 21, 2025

## What is x86_64?
- 64-bit version of the x86/IA32
instructon set
- CISC

## What is RISC?
- Reduced Instruction Set Computer

## What is CISC?
- Complex Instruction Set Computer

| | RISC | CISC |
| -- | ---- | ---- |
| registers | fewer | more |
| instruction | smaller, simpler | larger, complex operations in a singele step |

# x86_64 Notes - Aug 25, 2025

## Sections 
- `section .data`: initialized data, read + write
- `section .bss`: uninitialized data, read + write
- `section .text`: code segment, read + execute

```
High memory addresses
+-------------------+
|       Stack       |  ← grows downward (used for function calls, local vars)
+-------------------+
|       Heap        |  ← grows upward (dynamic memory: malloc/new)
+-------------------+
| .data / .bss      |
+-------------------+
| .text (code/instructions) |
+-------------------+
Low memory addresses

```

