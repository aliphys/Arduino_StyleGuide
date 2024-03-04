# Rules
- All variables must be initialized before use.
- Local variables should be defined at the point of first use, rather than at the beginning of a function
- Global and file-global variables should be grouped together and placed at the top of the source file, clearly separated from other variable declarations or function implementations.
- Any pointer variable not immediately assigned a valid address should be initialized to `NULL` 

# Examples
## Good example
```
// Good example
void setup() {
    // Initialize integer variables with 0
    int a = 0;
    int b = 0;

    // Initialize floating-point variables with 0.0
    float c = 0.0f;
    double d = 0.0;

    // Initialize boolean variables with false
    bool e = false;
}
```

## Bad example
```
// Bad example
void setup() {
    // Declare variables without initializing them
    int a;
    int b;
    float c;
    double d;
    bool e;
}
```

# Reasoning
- Initializing all variables before use prevents undefined behavior caused by accessing uninitialized memory.
- Defining local variables at the point of first use helps in understanding the program flow and ensures variables are used in their intended scope.
