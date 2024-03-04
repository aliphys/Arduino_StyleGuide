# Rules
- When the width in bits or bytes of an integer value is critical in the Arduino sketch, use fixed-width integer types instead of generic types like `char`, `short`, `int`, `long`, or `long long`.
- Use the signed (`int8_t`, `int16_t`, `int32_t`, `int64_t`) and unsigned (`uint8_t`, `uint16_t`, `uint32_t`, `uint64_t`) fixed-width integer types.
- Avoid using the keywords `short` and `long`.
- Restrict the use of the keyword `char` to the declaration of and operations concerning strings.

# Examples
## Good example
```
void functionExample() {
    // Good: Fixed-width integer type is used
    uint32_t counter; 
}
```

## Bad example
```
void functionExample() {
    // Bad: The width of 'long' is compiler dependent
    long counter; 
}
```

## Reasoning
- Using fixed-width integer types ensures consistent behavior across different Arduino platforms. For example, `int` could be 16 bits on some systems and 32 bits on others, but `int32_t` is always 32 bits.
- Fixed-width integer types make the code more self-documenting. When you see `uint32_t`, you know immediately that it's an unsigned 32-bit integer.
- They can help prevent bugs that might be caused by integer overflow or underflow. For example, if you add 1 to a `uint8_t` that's already at its maximum value of 255, it will wrap around to 0. If you were using `int` and expected it to become 256, you'd have a bug.
- Using `char` for non-string data can be confusing. It's better to use `int8_t` or `uint8_t` when you need a byte-sized integer.