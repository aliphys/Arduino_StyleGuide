# Rules
- All module names will consist purely of lowercase letters, numbers and underscores.  Spaces are not allowed within the module's header and source file names.
- A `.h` header file included inside the `src` folder with the same name as the library must exist. 
- No module header file can share the name of a reserved Arduino keyword.

# Examples
## Good example
- If a library is called `Arduino_UnifiedStorage`, then it includes a header file called `Arduino_UnifiedStorage.h`
- If a library is called `Arduino_MKRRGB`, then it includes a header file called `Arduino_MKRRGB.h`
- If a library is called `Timing`, then it includes a header file called `Timing.h`

## Bad example
- If a library is called `Arduino_UnifiedStorage`, then it includes a header file called `UnifiedStorage.h`
- If a library is called `Arduino_MKRRGB`, then it includes a header file called `Arduino_MKR RGB.h`
- If there is no header file included inside the `Timing\src` directory of a library called `Timing`

# Reasoning
- Ensure that module components are accessible across multiple platforms, irrespective of how cases and spaces are handled in the filenames
- Avoid name clashes with standard library headers and functions