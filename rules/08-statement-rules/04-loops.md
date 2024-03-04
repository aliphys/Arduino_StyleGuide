# Rules
- Avoid using magic numbers as the initial value or in the endpoint test of loops (while, do…while, for). Instead, use named constants.
- Except for initializing and updating a loop counter in a `for` loop, avoid assignments within the controlling expression of any loop.
- Implement infinite loops using the `for (;;)` or `while(true)` construct.
- The intent of infinite loops (apart from `void setup()` must be documented).
 
## Good example
```
for (int row = 0; row < MAX_ROWS; row++) {
    for (int col = 0; col < NUM_COLS; col++) {
        // Process each cell
    }
}
```

## Bad example
```
for (int row = 0; row < 100; row++) { // Avoid magic numbers
    
}
while(true) {
    // undocumented infinite loop
}

```
# Reasoning
- Using named constants instead of magic numbers ties the loop control explicitly to the data structure size or other logical limits, enhancing code readability and reducing the risk of errors when code or data structures change.
