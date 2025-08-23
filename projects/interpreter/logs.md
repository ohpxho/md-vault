
# Dev Logs - Aug 17, 2025
## Implementing substring function in C
> There are no existing implementation of substring like in java in C :(, so I gonna need to implement it on my own (I ask some help to chat-gpt for this hehe) 

> It took me a while to finish this since I am still confuse with pointers, eventually I was able to grasp the concept. And, it's not that hard.

```
char *substring(char *src, int start, int end) {
  if (!src) {
    return NULL;
  }

  int len = strlen(src); 

  if (start < 0 || end < 0 || start > end || start >= len || end >= len) {
    return NULL;
  }

  int curr = start;
  int substrLen = (end - start) + 1; // +1 for null terminator 
  char *substr = (char*)malloc(substrLen + 1); 
  
  if (!substr) {
    perror("Malloc Failed!");
    return NULL;
  }

  for (int i = 0; i < substrLen; i++) {
    substr[i] = src[curr];
    curr += 1;
  }
  
  substr[substrLen] = '\0';

  return substr;
}
```
 
> Checking bounds is really important to prevent unwanted errors

# Dev Logs - Aug 18, 2025
## Changes in substring function 
```
strncpy(substr, src, substrLen);

```
- I replaced the main loop in substring into the code above. 
- This function copies a specified number of string in the source to the destination. 

## Implementing isAtEnd function
> This returns if current chracter is the end of the source.

# Dev Logs - Aug 23, 2025

## Implementing  match function
- This function tell us if expected character matches the current character
- I just need to compare the expected character with `current` value since its value is incremented already
- I built this function initially with two characters as parameter: src, expected, but, this is incorrect
- Since the moment the characters matched, it needs to be consumed so I gonna need to increment the `current` pointer. If I put it inline the scanning function, it's just makes the condition larger so I put it inside the match function just like the sample in the book.

```
bool match(Scanner *scanner, char *expected) {
  if(isAtEnd(scanner)) return false;
  if(!scanner->source[current] == expected) return false;

  current++;
  return true;
}

```

## Implmenting peek function
- It just return the current character
- Easy


```
char peek(Scanner *scanner) {
  if(isAtEnd(scanner)) return '\0';
  return scanner->source[current];
}
```

## Dealing with comments
- This one is kinda tricky, since everything in line with `//` will be a comment and should be ignored

