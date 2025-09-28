# Review - Sept. 28, 2025
1. (5 pts) What's wrong with this code and how would you fix it?
int* create_array(int size) {
  int* arr = malloc(size);
  return arr;
}

```
Answer: 

The malloc will allocate the size of the array by bytes so if the size = 10, then the malloc will allocate 10 bytes to the array , which is incorrect since we were trying to allocate integers, which is 4 bytes of length

The correct code should be:
int* arr = malloc(size * sizeof(int));

This will allocate 10 integers NOT BYTES
```

2. (10 pts) Complete this function that safely allocates and
initializes an array:
int* safe_create_array(int count, int initial_value) {
  // Your implementation here
}

```
Answer:
int* safe_create_array(int count, int initial_value) {
    int* arr = malloc(count * sizeof(int));
    if(arr == NULL) {
        printf("%s\n", "Memory allocation failed.");
       exit(1); 
    }
    arr[0] = initial_value;
    return arr;
}

```

3. (10 pts) Explain what happens in memory when this code runs:
char* ptr1 = malloc(100);
char* ptr2 = ptr1;
free(ptr1);
*ptr2 = 'A';  // What happens here?

```
Answer:

```

Section 2: Struct Layout and Alignment (20 points)

4. (10 pts) Calculate the exact size and draw the memory layout:
struct mixed {
  char flag;
  int count;
  char status;
  double value;
};

```
Answer:
char flag = 1 byte
int count = 4 bytes
char satus = 1 byte
double value = 8 bytes
padding = 10

|char|__(3 bytes)___|int|status|___(7 bytes)____|double|

total size = 24 bytes

```

5. (10 pts) Reorder the struct members to minimize padding. What's
the new size?

Section 3: Pointers and Strings (25 points)

6. (10 pts) Fix this dangerous code:
void copy_string(char* dest, char* src, int max_len) {
  strncpy(dest, src, max_len);
}

7. (15 pts) Implement this function without using library functions:
// Returns length of string without counting null terminator
int my_strlen(const char* str) {
  // Your implementation
}

Section 4: Advanced Concepts (30 points)

8. (10 pts) What's the difference between these declarations?
char* str1;
char** str2;
When would you use each?

9. (10 pts) Complete this enum-based state machine:
typedef enum {
  STATE_IDLE,
  STATE_RUNNING,
  STATE_PAUSED,
  STATE_STOPPED
} ProgramState;

// Write a function that transitions between states safely
ProgramState transition_state(ProgramState current, int event) {
  // Your implementation
}

10. (10 pts) Debug this code - identify and fix the segmentation
fault:
struct Point {
  int x, y;
};

void update_point(struct Point* p) {
  p.x = 10;  // Line A
  p.y = 20;  // Line B
}

int main() {
  struct Point* ptr = NULL;
  update_point(ptr);  // Line C
  return 0;
}

Bonus Section (10 points)

11. (10 pts) Write a function that demonstrates both designated and
positional initialization:
struct Config {
  int timeout;
  char* name;
  int port;
  int debug;
};
