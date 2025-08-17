Interpreter
===

##Process Flow:
1. source code
2. lexical analyzer

##Scanner 
- store raw source code as simple string
- loops over the source and add token until the end of the string with the help of extra fields:
`
start = 0 (first character of the source)
current = 0 (current character in the source)
line = 1 (source line current is on)
`
- add "eof" token at the end (makes the parser little cleaner)
- additional helper functions: isAtEnd(if all characters are consumed)




