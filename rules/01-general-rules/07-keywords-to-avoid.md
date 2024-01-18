# Rule:
- Specific keywords should be avoided due to their potential to create confusion or lead to inefficient code. This extends beyond the traditional C++.
- Avoid using register for optimization purposes.

# Examples
## Good Example
```
int sensorValue = analogRead(sensorPin);
auto sensorValue = analogRead(sensorPin); // auto keyword allowed
```

## Bad Example
```
int Process = analogRead(sensorPin); // Process is reserved keyword
register int counter; // Avoid using 'register'
```

# Reasoning
The `auto` keyword, while prohibited in many C style guides is permissible in the Arduino Library Style Guide. It is included in C++11 onwards and should be possible to use across all Arduino Cores. The GCC compilers are (typically) better at optimizing code than manual attempts using keywords like register.