# Rules
- Variable names must not be reserved keywords of C, C++ and the Arduino language. 
- Variable names must not begin with an underscore. and must be less than 31 characters.
- Do not include numeric values that might change (e.g., array sizes or bit counts) in variable names to avoid misleading names if the numbers change.
- Ensure that variable names are descriptive of their purpose, avoiding vague or generic names.

# Examples
## Good examples
- `temperatureSensor`: A variable that represents a temperature sensor.
- `buttonState`: A variable that stores the state of a button.
- `ledPin`: A variable that holds the pin number of an LED.

## Bad examples
- `tempVal`: Does temp refer to temperature or temporary?
- `state`: State of what?
- `ledPin13`: The pin number should not be part of the variable name

# Reasoning
- Avoiding keywords and standard library names prevents naming conflicts and enhances code portability.
- Prohibiting names from starting with an underscore avoids clashes with names reserved for system or library use.