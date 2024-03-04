# Rules
- When naming new data types (such as classes, structs, and enums), use CamelCase convention and avoid underscores.
- In C++, `typedef` is not necessary for naming new structures, unions, and enumerations. Directly use the `struct`, `union`, or `enum` keyword followed by the name.
- Enumerations should be in all caps, with terms seperated by underscores
- The name for `struct`, `union`, or `enum` objects should include a `_s`, `_u` or `_e` at the end


# Examples
## Good example
```
# Examples
## Good example

```cpp
// Enum example
enum Color_e {
    LIGHT_RED,
    DARK_GREEN,
    BLUE
};

// Struct example
struct Point_s {
    int x;
    int y;
};

// Union example
union Data_u {
    int i;
    float f;
    char str[20];
};
```

## Bad example
```
// Enum bad example
enum colorE {
    Light_Red,
    dARK-Green,
    blue
};

// Struct bad example
struct point_S {
    int x;
    int y;
};

// Union bad example
union Data {
    int i;
    float f;
    char str[20];
};
```

# Reasoning
- `typedef` is not required for C++.
- Using `_e`/`_s`/`_u` at the end of data type names helps in distinguishing types from variables or functions.
