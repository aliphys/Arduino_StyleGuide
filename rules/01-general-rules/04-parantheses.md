# Rules
- Mandatory Use of Parentheses for Clarity: Parentheses should be used to clarify the execution order in a sequence of operations. This is especially important for operations involving logical AND (&&) and logical OR (||) operators.
- Surrounding Operands in Logical Operations: Unless it is a single identifier or constant, each operand of the logical AND (&&) and logical OR (||) operators shall be surrounded by parentheses. 

# Examples
## Good example
```
//parentheses with multiple logical operators
if ((sensorValue > lowerThreshold) && (sensorValue < upperThreshold)) {
    performAction();
}
while ((motorSpeed > 0) && (motorSpeed < maxSpeed)) {
    increaseSpeed();
}
```
## Bad example
```
//lacking parentheses with multiple logical operators
if (sensorValue > lowerThreshold && sensorValue < upperThreshold) {
    performAction();
}
while (motorSpeed > 0 && motorSpeed < maxSpeed || emergencyStop) {
    increaseSpeed();
}
```

# Reasoning
In complex expressions, especially those involving logical AND (&&) and OR (||) operators, the execution order can be ambiguous without parentheses. This ambiguity can lead to unintended behaviour and bugs in the library. When explicitly surrounding operands in logical expressions with parentheses, the intended order of evaluation is made clear. This is crutial for ensure long-term maintaince of libraries.

# Enforcement
During PR review and/or with cxxheaderparser