# Rule
- Single Statement per Line: No line of code should contain more than one statement.
- Natural Blocks of Code: Insert a blank line before and after each natural block of code, such as loops, if...else, and switch statements, and blocks of consecutive declarations
- Exception is when only one command is run for the control statement, which can optionally be in a single line

# Examples
## Good example
```
// Good Example
void loop() {
    int sensorValue = analogRead(A0);

    if (sensorValue > 500) {
        digitalWrite(LED_BUILTIN, HIGH);
    } else {
        digitalWrite(LED_BUILTIN, LOW);
    }

    delay(1000);
}

// Each statement on new line
int sensorValue = analogRead(A0);
Serial.println(sensorValue);

// Exception for one command in control statement
for (int i = 0; i < 10; i++) Serial.println(i);
```
## Bad example
```
void loop() {
    int sensorValue = analogRead(A0);
    if (sensorValue > 500) {
        digitalWrite(LED_BUILTIN, HIGH);
    } else {
        digitalWrite(LED_BUILTIN, LOW);
    }
    delay(1000);
}

// Multiple statement on single line
int sensorValue = analogRead(A0); Serial.println(sensorValue);
```

# Reasoning
- Readability and Organization: Blank lines can help identify segments of the control logic.
- Easier Maintenance: Clearly separated code blocks facilitate easier code maintenance and review, especially when new contributors/maintainers are involved.