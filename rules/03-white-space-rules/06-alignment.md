# Rule
- Variable and Struct/Union Member Names Alignment: Align the first characters of variable names within a series of declarations. Similarly, align the first characters of struct and union members.
- Assignment Operators Alignment: Within a block of adjacent assignment statements, align the assignment operators.
- Preprocessor Directives Alignment: The # in preprocessor directives should always be located at the start of a line, although the directives themselves may be indented within a #if or #ifdef sequence.

# Example
## Good Example
```
// Variable Alignment
int     sensorValue;
double  temperature;
char    status;

// Struct/Union Member Alignment
struct SensorData {
    int     value;
    char    type;
    double  accuracy;
};

// Assignment Operators Alignment
sensorValue  = readSensor();
temperature  = calculateTemp(sensorValue);
status       = checkStatus(sensorValue);

// Preprocessor Directives Alignment
#if defined(USE_SENSOR)
    #include <Sensor.h>
#endif
```

## Bad Example
```
// Variable misalignment
int      sensorValue;
 double    temperature;
char     status;

// Struct/Union Member misalignment
struct SensorData {
    int        value;
    char        type;
    double  accuracy;
};

// Assignment Operators misalignment
sensorValue  =  readSensor();
temperature  = calculateTemp(sensorValue);
status  = checkStatus(sensorValue);

// Preprocessor Directives misalignment
  #if defined(USE_SENSOR)
     #include <Sensor.h>
 #endif
```

# Reasoning
- Readability: Proper alignment enhances the readability of the code, making it easier to understand the structure and relationships between variables. Any changes involving the addition/removal of values can be done easily
- Maintainability: Consistent alignment helps in quickly identifying errors and understanding the code structure, especially important in a community-driven environment like Arduino.