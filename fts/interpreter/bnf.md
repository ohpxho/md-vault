# BNF Grammar of the Interpreter

## Components

1. `Terminals` - literals
2. `Nonterminals` - can be replaced with a concrete value, a placeholder
3. `Rules or Productions` - conventions of terminals and nonterminals that define how these elements relate

## Symbols

- `""` encloses a terminal symbol
- `<>` indicates a nonterminal symbol
- `()` indicates a group of valid options
- `+` specifies one or more of the previous element
- `*` specifies zero or more of the previous element
- `?` specifies zero or oe occurence of the previous element
- `|` indicates that you can select one of the options
- `[x-z]` indicates letter or digit intervals

_source: https://realpython.com/python-bnf-notation/_

```
<program> ::= <statement>
<statement> ::=
    | <expression> <statement>
    | <expression> <statement> <statement>
    | <expression> <statement> <statement> <statement>
```
