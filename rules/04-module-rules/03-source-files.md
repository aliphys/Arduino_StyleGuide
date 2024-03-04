# Rules
- Each source file in an Arduino library must control only one "entity" such as a data type, active object, peripheral driver, or communication protocol layer.
- The structure of a source file should include, in order:
  - a Doxygen comment block
  - include statements
  - definitions of data types
  - constants and macros
  - static data declarations
  - private function prototypes
  - public function bodies
  - private function bodies.
- Each source file must include its corresponding header file to allow the compiler to confirm that each public function and its prototype match.
- Do not use absolute paths in include file names.
- Remove unused include files from source files.
- Source files must not include other source files.

# Examples
## Good example
```
// Example of a well-structured source file
#include "myEntity.h" // Corresponding header file

// Definitions of data types, constants, and macros
#define MY_CONSTANT 42

// Static data declarations
static int myPrivateData;

// Private function prototypes
static void myPrivateFunction(void);

// Public function bodies
void myPublicFunction(void) {
    // Implementation
}

// Private function bodies
static void myPrivateFunction(void) {
    // Implementation
}
```

# Examples
## Bad example
```
// Example of a poorly structured source file
#include <stdlib.h> // Unrelated include
#include "mySource.c" // Including another source file

#define UNUSED -1 //  unused compiler directive

// Missing organization and inclusion of unrelated headers
void unrelatedFunction(void) {
    // Implementation
}
```

# Reasoning
- Structuring source files with a consistent order aids in readability and maintainability.
- Avoiding absolute paths and unused includes reduces dependencies and potential for errors.
- Enables future modular expansion with additional hardware and/or features