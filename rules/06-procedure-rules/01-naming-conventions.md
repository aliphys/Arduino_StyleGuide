# Rules
- Procedure names must not be reserved keywords of C, C++ and the Arduino language. 
- Procedure names must not begin with an underscore and must not be longer than 31 characters to ensure compatibility across different compilers, which might only recognize the first 31 characters.
- Procedure names must not be shorter than 3 characters, to ensure readability.
- Procedure names should not include numeric values that could change (e.g., the number of elements in an array or bits in a type), to avoid misleading information if those numbers change.
- Procedure names should be descriptive of their purpose, avoiding vague or generic names.

## Good example
```
void calculateTemperature() {
    // Code

void displayResult() {
    // Code 
}
```

## Bad example
```
void _calculateTemperature1() {
    // Code

void outThingy() {
    // Code 
}
```

# Reasoning
- Avoiding reserved keywords and standard library names prevents conflicts and confusion.
- Limiting the length of names and avoiding leading underscores respects compiler constraints and conventions across platforms