# C Notes - Aug 25, 2025

## Enums
- user-defined data type
- a way to assign or label integer contants
- **LIMITED TO INTEGERS ONLY**
```
enum day {
    SUNDAY,    // 0
    MONDAY,    // 1
    TUESDAY,   // 2
    WEDNESDAY, // 3
    THURSDAY,  // 4
    FRIDAY,    // 5
    SATURDAY   // 6
};
```
- by default, the first enumerator has value of 0, then will be incremented by 1, and will be assigned to the next enumerator
- values can be assigned manually
- using <mark>typedef enum</mark> is cleaner
```
typedef enum {
    RED,
    GREEN,
    BLUE
} Color;

// Now you can use Color instead of enum color
Color favorite = RED;
```

## Malloc
- in standard library functio <stdlib.h>
- allows you to allocate a block of memory in the heap
- always remember to free the memory allocated (it will persist unless explicitly freed) as it can lead to <span style="color: red">memory leak</span>.
- it return a pointer to the beginning of that memory block, with a return type of void * since it is untype (can be casted)
- if malloc fails, it returns NULL
- always check for null, after allocation
```
int* ptr = malloc(100 * sizeof(int));
if (ptr == NULL) {
    // Handle the error - don't continue!
    fprintf(stderr, "Memory allocation failed\n");
    exit(1);
}
```
- In the code below, the first one only allocates 10 bytes while the latter is 10 integers.

```
// BAD:
int* arr = malloc(10);  // Only 10 BYTES, not 10 integers!

// GOOD:
int* arr = malloc(10 * sizeof(int));  // 10 integers
```

C Notes - Aug 18, 2025
===

## strncpy 
- part of standard library <stdstring.h>
- copies specified number of string s from one string to another
- definition:

```
char *strncpy(char *dest, const char *src, size_t n);
```
- if n >= size of dest, it will not add a NULL terminator automatically, which will lead to buffer overrun
- in case that there are extra spaces in the dest after copy, all extra spaces will be filled with null bytes '\0'

# C Notes - Aug 24, 2025

## What is the size of this struct from a 64-bit computer?
```
struct x {
    int a;
    char b;
}
```
- The size is total of 8 bytes. why?
```
char = 1 byte
int = 4 bytes
padding = 3 bytes

|char|     |int|
----------------
```

## What is memory alignment in struct?
- Placement of data in the memory that can help CPU to access data efficiently
- The alignment process includes adding a padding in between data.
- The added padding is calculated based on the size of the largest alignment requirement, memory allocated should be multiple of that size
- The order of variables could affect the alignment.
- Aligned automatically by the compiler but can be  ommited 

```
A struct base address must be a multiple of its largest alignment requirement

E.g.

struct Example {
    char a;    // 1-byte aligned
    int  b;    // 4-byte aligned
    short c;   // 2-byte aligned
};

Offset 0:  a (char)    -> 1 byte
Offset 1–3: padding    -> to align `b` at offset 4
Offset 4–7: b (int)    -> 4 bytes
Offset 8–9: c (short)  -> 2 bytes
Offset 10–11: padding  -> to make struct size multiple of 4


You need to add a padding at the end to make the size a multiple of int 

```

- Processor doesn't read 1 byte at a time from memory, it reads **1 word** at a time. e.g. 32bit processor => 4bytes at a time

# C Notes - Aug 25, 2025

## Allocation in Stack and Heap
- allocation by default is stored in stack
- use `malloc` for heap allocations

## Limitation of switch
- It only works on integral types, so doing strings in switch, it will not compile

# C Notes - Aug 26, 2025
```
char **str
```
- This declation allows you to change the value in the original pointer pass to this.
- This will not create a local copy 

# C Notes - Aug 31, 2025
## Struct Initializer
- A method of initliazing values of a defined struct
- Two styles:
    - **Position Initializer**:
        ```
        struct Point {
            int x;
            int y;
        };

        struct Point p = {10, 20}; // x = 10, y = 20
        ```
        - Values are assigned by the order of the declation 
    - **Designated Initializer**:
        ```
        struct Point p = {.y = 20, .x = 10};
        ```
        - Explicit initilizing with properties of the struct named with dot
        - Order don't matter

## Aggregate types
- Types that is consist of multiple members. E.g. array, struct, union.

# C Notes - Sept. 07, 2025
## When does segmentation fault error occurs?
- When it tried to access a memory that is not allowed to access.
```
Dereferencing NULL pointers

int *ptr = NULL;
*ptr = 5;  // Segfault - accessing address 0

There are more other examples...
```

## When to use dot operator(.) or arrow operation(->) in accessing a member of a struct?
- Struct variable: dot operator
```
struct Point {
    int x;
    int y;
};

struct Point p;  // This is a struct variable
p.x = 10;        // Use dot to access members
p.y = 20;
```
- Pointer to a struct: arrow operator
```
struct Point *ptr;  // This is a pointer to a struct
ptr = &p;           // Point to our struct
ptr->x = 30;        // Use arrow to access members
ptr->y = 40;
```
# C Notes - Sept. 28, 2025
## Identifying the value from a void * variable
- There are no direct way to know the type since type information is lost on void *
- You need to manually define the type and cast it 

## UNION
- This is like a struct, the only difference is that all members share the same memory with the largest element as their size 
- Let you store different types in the same varible, buto nly one at a time

```
union Data {
    int i;
    float f;
    char c;
};
```

# c Notes - Oct. 5, 2025

## When to use -> and . operations?
- Use `->` when your access to a struct is through a pointer
- Use `.` when you are trying to access the actual struct implementaton 

