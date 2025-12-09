# Dec 05, 2025 - Review

Here are two sets of questions based on the provided notes for Chapter 1 - Style:

---

## Set 1: Foundation-Building Questions

1.  According to the notes, what is the single most important criterion for judging good programming style?

Answer:

```
Ease of reading, all the styles mentioned are considered to improve the readability of the code
```

2.  List three essential attributes a good name in programming should possess.

Answer:

```
1. Consistent
2. Accurate
3. Pronouncaeble
```

3.  When is it appropriate to use shorter, less verbose names for variables, according to the notes?

Answer:

```
For shorter, less verbose names are proper for local variables. Too long can cause loss of clarity.
```

4.  Explain why naming elements like `queueCapacity` within a `UserQueue` class is considered redundant. Provide an example of how this could be improved without losing clarity.

Answer:

```
since the queueCapacity refers already to the queue, doing UserQueue.queueCapacity feels redunadant and unnecessary. By changing it into `capacity` reading UserQueue.capacity is more natural.
```

5.  What kind of words are recommended for naming functions that perform an action? Give an example of such a function name.

Answer:

```
For naming functions, you should follow verb + noun format. Since it is a function that perform an action a verb is appropriate to make its intentions clear
```

6.  How should the name of a function clearly indicate that it returns a boolean value? Provide an example.

Answer:

```
For boolean function, you can prefix the name with `is`. This helps to indicate that the function return a boolean value
```

7.  Why is maintaining a consistent naming format (e.g., `isLoggedIn` vs. `loggedIn`) across a codebase crucial?

Answer:

```
It eases the readability of the code, with consistent format you can relate variables or functions easily.
```

8.  How does proper indentation contribute to the "ease of understanding" a program's structure?

Answer:

```
Indentation helps by identifying scopes.

if(x){
x += 1;
y = x;
}

is harder to read than

if(x) {
    x += 1
    y = x;
}

speacially if you have larger codebase.
```

9.  Why is it advised to write conditional expressions in their "natural or positive state" rather than relying on negations?

Answer:

```
Because negations is harder to read that its positive form due to it increases cognitive load and the two-step mental process.
```

10. In what situations should parentheses be explicitly used in expressions, even if operator precedence rules might suggest they are optional?

Answer:

```
For long operations, having parenthesis to group related operations
```

11. What strategy is recommended for handling operations that are complex or involve multiple steps within a single expression?

Answer:

```
This can be done by chaining if-else statements
```

12. Briefly define "side effects" in the context of programming and explain why programmers should exercise caution when dealing with them.

Answer:

```
Side effects are unintended processese that is being executed out of the scope of your program. For example, handling IO operations or any external libraries may return unexpected results or affect that can impact the program.
```

13. What is an "idiom" in programming style, and how do established idioms benefit a codebase?

Answer:

```
Idioms are conventions used by experience programmers that is considered good practice in the programming language
```

14. Describe a scenario where an `else-if` chain is the more appropriate choice for handling multi-way decisions compared to a `switch-case` statement.

Answer:

```

```

15. Conversely, describe a situation where a `switch-case` statement is generally preferred over an `else-if` chain for multi-way decisions.
16. What is the primary recommendation regarding the use of function macros?
17. If function macros _must_ be used, what two specific parenthesization rules are critical to follow for their body and arguments?
18. What is a "magic number," and what is the recommended practice for incorporating such values into your code?
19. Why should numeric constants typically be defined using the `const` keyword rather than preprocessor macros (`#define`)?
20. What is the fundamental purpose of a good comment, and what type of information should it primarily convey about the code?

---

## Set 2: High-Difficulty Synthesis Questions

1.  The overarching criterion for good style is "ease of understanding." Discuss how rules pertaining to naming accuracy, expression clarity (e.g., avoiding negations, breaking up complexity), and appropriate commenting all contribute synergistically to this single goal. Provide specific examples from each area to illustrate your points.
2.  Imagine you are reviewing a codebase where developers have consistently used "clever" constructs and highly condensed expressions to minimize line count. Analyze the long-term consequences of this "cleverness" on maintainability, debugging, and onboarding new team members, contrasting it with the principles of clarity and breaking up complex operations.
3.  The notes advise against using long variable names "regardless of context," suggesting that "clarity is often achieved through brevity." Construct an argument for when extreme brevity in naming might actually _decrease_ understanding, even for local variables, and articulate scenarios where a longer, more descriptive name is unequivocally superior.
4.  You are tasked with refactoring a critical function containing a single, deeply nested conditional expression that uses multiple logical operators, bitwise operations, and negations. Outline a step-by-step process to apply the style rules of "natural form," "parenthesize to resolve ambiguity," and "break up complex operations" to this expression, without altering its logical outcome.
5.  A new programming language gains popularity, and its community heavily promotes a style where functions are almost exclusively implemented as "one-liners" using functional programming constructs that might be unfamiliar to mainstream programmers. Discuss the potential benefits and drawbacks of adopting such a style in a team setting, particularly in light of the "consistency and idioms" rule and the primary criterion of "ease of understanding."
6.  Explain the fundamental reasons _why_ parenthesizing the body and arguments of function macros is crucial. Provide a concrete C-like example for each case (body and argument) that demonstrates a subtle bug or unexpected behavior that would arise from omitting the parentheses.
7.  Beyond mere stylistic preference, discuss the technical advantages of using `const` variables over `#define` preprocessor macros for defining numeric constants. Consider factors such as type safety, debugging information, scope, and the compiler's ability to perform optimizations.
8.  The notes state, "Don't comment bad code, rewrite it." While ideal, real-world constraints sometimes prevent immediate rewrites. Propose specific scenarios (e.g., extreme time pressure, legacy system with no budget for major refactor, temporary workaround) where adding a _specific kind_ of comment about "bad code" might be a pragmatically necessary, albeit temporary, solution. How would such a "bad code" comment differ in purpose and content from a genuinely helpful comment?
9.  Consider the interplay between `if-else if` chains and `switch-case` statements. Beyond their recommended use cases, discuss the potential impact of each construct on code extensibility. For instance, how might adding a new condition or case affect the existing structure, readability, and potential for bugs in both implementations?
10. Reflect on how a deliberate focus on good naming conventions, clear expression construction, and consistent structure can significantly _reduce_ the necessity for many comments. Provide examples where the code itself, through good style, becomes largely "self-documenting," thereby adhering to the principle that comments should "add something not immediately evident."
11. Imagine you are integrating a third-party library that follows significantly different style guidelines than your project. Discuss the trade-offs of adapting the library's style to match yours versus maintaining its original style, considering the principles of consistency, ease of understanding, and the practical implications for development and maintenance.
