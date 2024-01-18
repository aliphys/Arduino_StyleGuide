# Rule
- Single Statement per Line: No line of code should contain more than one statement.
- Natural Blocks of Code: Insert a blank line before and after each natural block of code, such as loops, if...else, and switch statements, and blocks of consecutive declarations
  - Exception is when only one command is run for the control statement

# Examples
```
// Good Example
for (int i = 0; i < 10; i++) {
    // Do something
}

// Do next thing

// Needs Improvement
for (int i = 0; i < 10; i++) {
    // Do something
}
// Do next thing
```

# Reasoning
- Readability and Organization: Blank lines can help identify segments of the control logic.
- Easier Maintenance: Clearly separated code blocks facilitate easier code maintenance and review, especially when new contributors/maintainers are involved.