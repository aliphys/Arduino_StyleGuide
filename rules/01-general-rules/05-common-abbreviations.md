# Rule
- In Arduino code, abbreviations and acronyms should be avoided unless they are widely and consistently understood.
- If needed, a table of project-specific abbreviations and acronyms should be maintained in the documentation.

# Examples
## Good examples
```
int temperatureSensorReading; // Clear and descriptive
bool powerLED; // LED is common abbreviation
```
## Bad Examples
```
int tmpSR; // temp could mean temporary or temperature
bool powerLightEmittingDiode; // no need to write LED in full
```

# Reasoning
Limit abbreviations and acronyms in Arduino code, except for widely recognized ones, ensures clarity and minimizes ambiguity. Clear and descriptive names, enhance understandability and readability, making the code more accessible to developers of varying expertise including new contributors. 