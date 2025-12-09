# SICP Notes

## Chapter 1

## The Elements of Programming - Chapter 1.1

### Core Elements of a Programming Language

1. `Primitive Elements`
   - Primitive Data: numbers, symbols, basic values
   - Primitive Procedures: +, -, /, basic built-in operations, etc.

```
Complexity starts from simplicity
```

2. `Means of Combination`
   - Building complex expresions from simpler ones by combining them

```
Complexity grows by combining simple procedures and data into larger units.
```

3. `Means of Abstraction`
   - This allows you to treat a series of procedure or a complex ideas into a single concept (E.g. square a number)
   - Abstraction allows you to name things: values, expressions, ad procedures. This reduces complexity and makes code understandable.

```
Abstraction creates a mental building blocks so you can think at a higher level
```

### Special forms

- Not everything follows the rule of evaluating all subexpressions
- Take for example: `define`, `if`, this primitive procedures behave differently than other primitive procedures. **They do not evaluate, but control the evaluation**

### Procedural Abstraction

- Hiding details in a named procedure/ function and treat it like a black box.

## Procedures and the Processes They Generate - Chapter 1.2

```
The ability to visualize the consequences of the actions under consideration is crucial to becomning an expert programmer
```

- `Linear Recursion`: each calls waits for the next call to finish, memory grows linearly with input size.
- `Linear Iteration`: uses constant memory; loops

### Difference between Recursive Process vs Recursive Procedures

- `Recursive Procedure` - a procedure that calls itself (syntactic)
- `Recursive Process` - a process that builds up deferred operations - a grwoing call stack

### Tail Recursive Optimization

- A recursive procedure where the recursion is the last operation to perform by the procedure/function
- This optimization is done by compilers where they re-use stack frames instead of pushing another when a recursive call happens
- This optimization make the space usage contant instead of linear as other recursive procedure consumes
- This optimization does not apply to all , it depends, if the compiler supported it (E.g. python does not support this).

```
A recursive procedure does not necessarily generate a recursive process
```
