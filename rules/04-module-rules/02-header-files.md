# Rules
- Each Arduino library must include exactly one header file for every source file, sharing the same root name.
- Every header file must have preprocessor guards to prevent multiple inclusions.
- Header files should declare only the necessary procedures, constants, and data types (through prototypes, `#define` statements, and `typedefs`) that other modules need to know about.
  - It is recommended to avoid declaring variables (using `extern`) in header files.
  - No variable storage should be allocated in a header file.
- Public header files must not `#include` any private header files.

# Examples
## Good example
```
#ifndef __ARDUINO_GIGADISPLAYTOUCH_H
#define __ARDUINO_GIGADISPLAYTOUCH_H
// Declarations of functions, constants, and types
#endif /* __ARDUINO_GIGADISPLAYTOUCH_H */
```

## Good example
```
// No preprocessor guard, potentially leading to multiple inclusion issues
// Includes a private header file, which should not be exposed
#include "privateHeader.h"
```

# Reasoning
- Using a single header file for each source file with matching names simplifies the management of library modules and their interdependencies.
- Preprocessor guards prevent multiple inclusions of the same header file, avoiding compilation errors.
- Excluding private headers from public headers maintains encapsulation.