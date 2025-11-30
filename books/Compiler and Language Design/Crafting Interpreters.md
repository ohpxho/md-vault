# Crafting Interpreter

## Representing Code - Chapter 2

### Context-Free Grammar (CFG)

- `regular language` - rule for how characters get grouped into tokens
- A set of rules that defines the structure of a language

| Terminology    | Lexical grammar  | Syntactic grammar |
| -------------- | ---------------- | ----------------- |
| `alphabet`     | characters       | tokens            |
| `string`       | lexeme or token  | expression        |
| implementation | lexer or scanner | parser            |

- valid strings(`derivations`) can be formed by following the rules(`productions`) set out in the grammar
- Each rule in CFG has a **head** and a **body**. The head is the token which the rule produces, and the body is the sequence of tokens which make up the rule.
- Allows you to generate infinite number of strings with finite number of rules

### Two flavors of symbols:

- `Terminal` - A token, literal value. E.g if, 123
- `Nonterminal` - A variable that represents a grammar rule. E.g S, A, B

### Diferrence between regular and context free grammar

|                     | Regular Grammar                  | Context Free Grammar                                      |
| ------------------- | -------------------------------- | --------------------------------------------------------- |
| Usage               | For simple patterns (no nesting) | For structural languages (supports nesting and recursion) |
| Automata            | Finite                           | Pushdown                                                  |
| Memory              | No memory needed                 | Pushdown automata - has a stack for memory                |
| Hierarchy (Chomsky) | Type-3                           | Type-2                                                    |

### BNF - Backus-Naur Form

- A metasyntax(a syntax used to define the syntax of a programing language) notation for context-free gramars.
- A Formal method for describing the syntax of a programming language.
- A nonterminal must have their own defining rules.
- **:=** means `may expand into` and `may get replaced with`
- `|` is the `or` operator
- `*` is the `zero or more` operator
- `+` is the `one or more` operator
- `?` is the `zero or one` operator
- name or nonterminal symbol are enclosed with `<>`
