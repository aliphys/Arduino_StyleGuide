# Rules
- Mandatory Use of Parentheses for Clarity: Parentheses should be used to clarify the execution order in a sequence of operations. This is especially important for operations involving logical AND (&&) and logical OR (||) operators.
- Surrounding Operands in Logical Operations: Unless it is a single identifier or constant, each operand of the logical AND (&&) and logical OR (||) operators shall be surrounded by parentheses. 

# Examples
```
// Good Example
if ((sensorValue > lowerThreshold) && (sensorValue < upperThreshold)) {
    performAction();
}

// Needs Improvement
if (sensorValue > lowerThreshold && sensorValue < upperThreshold) performAction();
```

# Reasoning
- Clarity and Avoiding Errors: The C language, which Arduino sketches are based on, has many operators with complicated precedence rules. This becomes more complicated, when the logical state of hardware is also taken into account for. Explicitly using parentheses helps ensure that operations are carried out in the intended order, reducing the risk of bugs. Especially, due to the multi-platform nature of code
- Ease of Understanding: Parentheses make it easier for other programmers to understand the logic of the code, which is vital in the Arduino community where code is often shared and modified by others.