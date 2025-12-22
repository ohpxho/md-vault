# Context Free Grammar Notes

- What is CFG?
- What are the parts of a CFG?
- What is a `sentential form`?
- What is the difference between `terminal` and `non-terminal` symbols?
- What is the difference between `derivation` and `production`
- Why does the rules in CFG required a head and a body?
- What does the head holds?
- What does the body holds?
- How many strings can you generate with CFG given a finite number of rules?
- How can CFG generate an unlimited number of strings from finite number of rules?
- Why does CFG needs a memory? And, how it is implemented?
- What data structure is needed for CFG? And, why?
- How does CFG supports structural languages?
- What hierarchy in Chomsky does CFG falls under?

## Left Recursion

- What is left recursion?
- How can you say that the derivation is left recursive?
- Why does left recursion pose a significant problem for recursive descent? And, what is the problem?
- How does left recursion can be resolved?

## Parsing Techniques

- What are the two fundamental approach of parsings CFG?
- What is the difference between LL(1) and LR(1)?
- What is the difference between direct and indirect left recursion? And, why is the distinction important?
- What is the importance of CFG in language design?
- How can you identify ambigutieties in a grammar?

## LL Grammars

- How does LL(1) or recursive descent parse CFG?
- How to say that a grammar is LL(1)? And, what are its properties?
- Why does we need to eliminate left recursion when using LL(1) grammar?
- How will you construct an LL(1) grammar?
- How will you eliminate common left prefixes? And, why?
- What is a lookahead token?
- How many lookaheads is needed? Can you increase it? What are the implications of increasing it?

## LR Grammars

- How does LR(1) parse CFG?
- Why does LR(1) is more powerful than LL(1)?
