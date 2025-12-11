# Introduction to Compilers and Language Design

## Scannings - Chapter 3

### Kinds of Tokens

Most languages will have token in these categories:

1. `Keywords` (what makes up the structure of the language such as while, for, true, class, etc.)
2. `Identifiers` (names of variables, functions, classes, and other code elements)
3. `Numbers` (integers, floating point values, or fractions, or in alternate bases such as binary, octal, etc.)
4. `Strings` (character sequence usually quoted with single or double quotes, but also must have some facility for containing quotations, newlines, and unprintable characters)
5. `Comments and whitespace` (important notes but not part of evaluation and format)

- In language design, prioritize to design the keywords that will build the structure of the language
- Basic Approach: `Read one character at a time with maximal munching to identify tokens`; Formal approach: `Utilize RE & FAs for precise identification of tokens`

### Regular Expression

- Language for expressing patterns in text

### Finite Automata

### Deterministic Finite Automata

### Nondeterministic Finite Automata

### Conversion Algorithms

### Convertings REs to NFAs

### Minimizing DFAs

### Limits of Finite Automata
