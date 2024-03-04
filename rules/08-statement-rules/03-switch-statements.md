# Rules
- Align the `break` statement of each case with the case label, not with the case block's contents.
- Ensure all switch statements include a default case.
- Explicitly comment on any intentional fall-through between cases to clarify the absence of a `break` statement.

# Examples
## Good example
```
switch (errorCode) {
    case ERROR_CODE_A:
        // Handle error A
        break;
    case ERROR_CODE_B:
        // Handle error B
        // Fall through to ERROR_CODE_C is intentional
    case ERROR_CODE_C:
        // Handle error C
        break;
    default:
        // Handle unknown errors
        break;
}
```

## Bad example
```
switch (errorCode) {
    case ERROR_CODE_A:
        // Handle error A
        // Missing break, potentially unintentional fall-through
    case ERROR_CODE_B:
        // Handle error B
        break;
    // No default case, potential unhandled cases
}
```

# Reasoning 
- Proper alignment and documentation of break statements make it easier to identify control flow within switch statements, reducing the risk of errors.
- Including a default case ensures that all possible values are considered, preventing unhandled cases.
