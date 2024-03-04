# Rules
- Try to minimize the use of floating-point constants and variables. Consider alternatives like fixed-point math or integer operations which are more efficient on Arduino.
- If you must use floating-point calculations:
    - Declare floating-point variables explicitly as `float` (for single precision) or `double` (for double precision).
    - Avoid direct equality or inequality comparisons between floating-point numbers due to the imprecise nature of floating-point representation. Instead, use a small range to check if values are approximately equal.

# Examples
## Good example
```
// Define two int variables
int a = 1 * 10;
int b = 10;


if (a == b) {
    Serial.println("The numbers are equal.");
}
else {
    Serial.println("The numbers are not equal.");
}
```

## Bad example
```
// Define two float variables
float a = 0.1 * 10;
float b = 1.0;


if (a == b) {
    Serial.println("The numbers are equal.");
}
else {
    Serial.println("The numbers are not equal.");
}
```

## Reasoning
- Performing calculations with floating-point math is slower than using integer math.
- Calculations in integer values prevents undefined behavior from propagating through the library.
- Imprecise nature of floating point numbers can cause lead to conditional terms being calcuated incorrectly
