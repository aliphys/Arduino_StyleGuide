# Rules
- Do not define bit-fields within signed integer types.
- Avoid using bitwise operators (&, |, ~, ^, <<, and >>) on signed integer data.
- Do not mix signed and unsigned integers in comparisons or expressions. Ensure that decimal constants intended to be unsigned are suffixed with 'u'.

# Examples
## Good example
```
uint16_t unsignedInt = 6u; // Correct: Unsigned integer with 'u' suffix
int16_t signedInt = -9; // Correct: Signed integer for negative values

if ((unsignedInt + signedInt) < 10u) {
    // Correct: Mixing unsigned and signed integers in an expression correctly
}
```

## Bad example
```
int unsignedInt = 6; // Incorrect: Should be unsigned or suffixed with 'u' for clarity
int signedInt = -9; // Potential confusion: Better to explicitly use a signed type like int16_t

if (unsignedInt + signedInt < 10) { // Incorrect: Mixing without clear unsigned indication
    // This can lead to unexpected behavior due to implicit type conversions
}

```

# Reasoning
- Bit-fields within signed integer types can lead to unexpected behavior due to the way negative numbers are represented in binary.
- Bitwise operators on signed integers can also lead to unexpected results due to sign extension. 
- Mixing signed and unsigned integers in comparisons or expressions can lead to subtle bugs due to the way C++ performs implicit type conversions. There could also be differences between platorms, affecting the portability of the Arduino library
- Using the 'u' suffix on unsigned decimal constants makes it clear that the constant is intended to be unsigned. This can help prevent bugs and make the code easier to understand.