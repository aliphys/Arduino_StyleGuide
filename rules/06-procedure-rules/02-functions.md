# Rules
- Each function can be a maximum of a maximum of 100 lines
- Preferably, all functions should have just one exit point, ideally via a return statement at the bottom of the function.
- Declare a prototype for each public function in the module header file
- Declare all private functions as static to enforce encapsulation and limit their scope to the file in which they are declared.
- Explicitly declare and meaningfully name each parameter

# Examples
## Good example
```
// well-designed function 
int calculateSum(int a, int b) {
    int result = a + b;
    return result; // Single exit point
}
```

## Bad example
```
// Poorly designed function
int calculate(int a, int b) { 
    if (a > b) return a + b; // Multiple exit points
    else return a - b;
}
```

# Reasoning
- Keeping functions short and to the point makes the code easier to understand, review, and debug.
- Functions with a single exit point are simpler to trace and debug, enhancing code quality.