# Rules
- The minimum supported C++ syntax across all platforms is C++11. However, depending on the chosen Arduino core, it may provide access to additional features and capabilities from newer C++ standards.
- The use of assembly code should be limited to the library src folder (e.g. `.h` and `.cpp` files) and must not be used in example sketches.
- The preprocessor directive #define must not be used to alter or rename any C++ or Arduino language keyword or other programming language aspects.
- The different Arduino cores have varying levels of support for C++ syntax as follows

| Arduino Core        | C++ Version Supported |
| ------------------- | --------------------- |
| ArduinoCore-avr     | C++11                 |
| ArduinoCore-samd    | C++11                 |
| ArduinoCore-mbed    | C++14                 |
| ArduinoCore-renesas | C++17                 |

# Example
## Good examples
```
#define LED_INDICATOR 13       // OK, if inside .cpp/.h files
#define MAX_SENSOR_VALUE 1023  // OK, if inside .cpp/.h files
// range based loop included in C++11, syntax supported by all Arduino cores
int array[5] = {100, 200, 300, 400, 500};
for (int element : array) {
    digitalWrite(LED_BUILTIN, HIGH); // Turn the LED on
    delay(element);                  // Wait for 'element' milliseconds

    digitalWrite(LED_BUILTIN, LOW);  // Turn the LED off
    delay(element);                  // Wait for 'element' milliseconds
}
// inline variable (C++17 feature) used with ArduinoCore-renesas library
inline int sharedValue = 42;
```
## Bad examples
```
#define LED_INDICATOR 13       // Bad, if inside .ino sketches
#define MAX_SENSOR_VALUE 1023  // Bad, if inside .ino sketches
int LED_BUILTIN = 13          // LED_BUILTIN is reserved keyword
#define analogRead default    // analogRead() is a builtin ADC function
#define true FALSE            // please don't
// inline variable (C++17 feature) used with ArduinoCore-avr/samd/mbed library
inline int sharedValue = 42;
```

## Reasoning
All Arduino platforms support at least C++11, ensuring a consistent baseline. Developers can use efficient and readable C++11 features universally, while also taking advantage of more advanced features in newer standards when working with specific cores. Restricting assembly code (and compiler directives such as #DEFINE) to library source files (.h and .cpp) rather than example sketches ensures that the lower-level, platform-specific optimizations are confined to areas where they can be managed by experienced developers. This maintains the accessibility and simplicity of the Arduino platform for a wider audience, including hobbyists and educators. Additionally, the abstraction allows for easier use of the libraries increasing developer efficiency. 