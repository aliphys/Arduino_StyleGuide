# Rules
- Place the shortest branch of an `if` or `else if` statement first.
- Avoid nested `if…else` statements deeper than two levels. Instead, use function calls or switch statements to simplify logic.
- Do not perform assignments within the condition of an `if` or `else if` statement.
- Always conclude an `if` statement with an `else if` branch with an `else` clause to cover all possible outcomes.

# Examples
## Good example
```
if (isConnected()) {
    connect();
}
else if (isAttemptingToConnect()) {
    // Attempt to connect
}
else {
    // Handle not trying to connect
}
```

## Bad example
```
if (sensorValue > 100) // Complex logic
{
    // Do something complex
}
else if (sensorValue > 50) {
    // Nested if
    if (anotherCondition) {
        // More nested logic
    }
}
// Missing final else clause

```

# Reasoning
- Structuring conditional statements in this manner aids in understanding the logic flow, especially for developers new to a project or those reviewing code for potential integration with Arduino hardware and software.
- Reducing nested conditions, increases code portability and creation of unit tests

