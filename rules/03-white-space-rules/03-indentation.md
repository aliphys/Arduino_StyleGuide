# Rule
- General Indentation: Each indentation level should align at a multiple of 4 spaces from the start of the line.
- Switch Statements: Within a switch statement, the case labels shall be aligned; the contents of each case block shall be indented once from the case labels.
- Long Lines: When a line of code is too long to fit within the maximum line width, it should be indented in the most readable manner possible.
- Readme: Markdown files are exempted from the indentation rules

# Examples
## Good Example
```
// Indentation with four spaces
for (int i = 0; i < 10; i++) {
    doSomething();
}

// Switch Statement Indentation
switch (sensorType) {
    case TEMPERATURE:
        readTemperatureSensor();
        break;
    case PRESSURE:
        readPressureSensor();
        break;
}

// Long Line Indentation
longFunctionCallWithLotsOfParameters(param1, param2, param3,
                                     param4, param5, param6);
```

## Bad Example
```
// Indentation with incorrect spaces
for (int i = 0; i < 10; i++) {
         doSomething();
}

// Misaligned Switch Statement Indentation
switch (sensorType) {
        case TEMPERATURE:
        readTemperatureSensor();
        break;
        case PRESSURE:
        readPressureSensor();
        break;
}

// Misaligned Long Line Indentation
longFunctionCallWithLotsOfParameters(param1, param2, param3,
                                        param4, param5, param6);
```

# Reasoning
- Readability and Consistency: Indentation helps with readability, especially when long code exists over multiple lines
- Easier Navigation and Maintenance: Proper indentation aids in understanding the structure of the code, making it easier to navigate and maintain with IDE/terminal shortcuts