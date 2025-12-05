# The Practice of Programming Notes

## Chapter 1 - Style

```
The proper criterion is ease of understanding
```

### Name

- _A name should be informative, concise, memorable, and pronounceable if possible._
- Rule: `Descriptive names for global functions, classes, and structures. And, shorter names suffice for local variables`

```
Programmers are often encouraged to use longs variable names regardless of context. That is a mistake: clarity is often achieve through brevity.
```

- Rule: `Be Consistent`

  - Opt for a single format (E.g. noOfItems, noOfUsers)
  - Don't be redundant

  ```
  Class UserQueue {
      int frontOfQueue, queueCapacity
  }

  This is redundant, does not need to mention queue

  Class UserQueue {
      int front, capacity
  }

  No clarity is lost
  ```

- Rule: `Use active names for functions`
  - Should be based on active verbs, perhaps followed by nouns (E.g getTime, checkTotal)
  - For functions that returns a boolean, ensure that it makes clear that it returns a boolean value (E.g isOctal, isBalanceSufficient)
- Rule: `Be accurate`
  - Names are not only labels, they convey information.
  - Describe accurately what the function class, function, variable represent or does.

### Expressions and Statements

- Rule: `Indent to show structure` (This makes the structure of the program more self-evident)
- Rule: `Use the natural form for expressions`
  - Instead of using negations, write them in natural or positive state
  - Conditional expresson that include negations are always hard to understand
- Rule: `Parenthesize to resolve ambiguity`
  - Specify the groupings for more clear intentions
  - Take note of the precedence of the operations (E.g bitwise operators have lower precedence than relational operators)
- Rule: `Break up complex operations`
  - Do not cram a complex operations into one expression because it is easier to grasp if it is broken into several pieces.
- Rule: `Be clear` (not clever)
- Rule: `Be careful with side effects`

### Consistency and Idioms

```
Consistency leads to better programs
```

- Rule: `Use a consistent identation and brace style`
- Rule: `Use idioms for consistency` (conventinoal ways that experienced programmers write common pieces of idioms)
- Rule: `Use else-ifs for multi-way ecisions`
  - For evaluating compex conditions, ranges of values, or conditions involving multiple variables, use if-else
  - For performing actions based on the exact value of a single variable, use switch-case

### Function Macros

- Rule: `Avoid fnuction macros`
- Rule: `Parenthesize the macro body and arguments`

### Magic Numbers

- Rule: `Give names to magic numbers`
- Rule: `Define numbers as constants, not macros`
- Rule: `Use character contants, not integers`
- Rule: `Use the language to calculate the size of an object`

### Comments

- Rule: `Comment should add something not immediately evident from the code`
- Rule: `Add comments in function and global data`
- Rule: `Don't comment bad code, rewrite it` (Do this when the comment outweighs the code)
- Rule: `Comments should agree and support the code` (If you change the code, ensure that the coresponding comment is still relevant or accurate)
