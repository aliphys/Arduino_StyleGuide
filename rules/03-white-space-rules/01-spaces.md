# Rules
- Keywords: if, while, for, switch, and return should be followed by one space when additional program text is on the same line.
- Assignment Operators: Operators like =, +=, -=, *=, /=, %=, &=, |=, ^=, != should be preceded and followed by one space.
- Binary Operators: Operators such as +, -, *, /, %, <, <=, >, >=, ==, !=, <<, >>, &, |, ^, &&, || should be preceded and followed by one space.
- Unary Operators: Operators like +, -, ++, --, !, ~ should not have a space on the operand side.
- Pointer Operators: * and & should have white space on each side within declarations but no space on the operand side elsewhere.
- Ternary Operator: The ? and : characters should each always be preceded and followed by one space.

# Examples
## Good example
```
if (sensorValue > threshold) {
    action();
}

int result = a + b;
```
## Bad example
```
if(sensorValue>threshold){
    action();
}

int result=a+b;
```

# Reasoning
- Readability and Clarity: Proper use of spaces enhances code readability and clarity, making it easier to understand and maintain. It can also help with dyslexic readers → https://dev.to/codemouse92/comment/mb03
- Consistency: Consistent spacing in operators and keywords ensures uniformity across the Arduino codebase, aiding in collaboration and review.