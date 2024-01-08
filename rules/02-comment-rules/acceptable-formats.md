# Rule
- Comment Styles: Use single-line (C++ style, //) and multi-line (traditional C style, /* ... */) comments.
- Javadoc Style for API Documentation: Document classes and functions using Javadoc style format comments.
- Inline Comments: Use /// for single-line comments within functions or blocks.
- Member Documentation: Use ///< for documenting members on the same line.
- Handling Commented-Out Code: Avoid commenting out code; use conditional compilation (#if 0 ... #endif) instead.
- Where to Document API:
  - Header Files: Document usage in header files where declarations are made.
  - Source Files: Document function workings in source files, inline where appropriate.
- Comment objective: Provide useful information beyond the obvious, such as usage scenarios, limitations, and additional functionality details

# Examples

```
// Single-line comment
// Initializes the sensor

/* Multi-line comment
 * Sets default threshold values
*/

/// Inline comment for detailed explanation within a function

enum class IndoorAirQualitySensorMode {
    POWER_DOWN = 0, ///< Mode to turn off the sensor and reduce power consumption
    CLEANING = 1, ///< Cleaning mode to perform a thermal cleaning cycle of the MOx element
    INDOOR_AIR_QUALITY = 2, ///< Mode to measure indoor air quality
};
```

API Documentation Markup:

    @author: Denotes the author of the software.

    @param: Documents parameters with [in], [out], [in,out] to indicate direction of data.

    @return: Describes the return value and type.

    @see: Refers to related documentation (e.g., String#toLowerCase()).

    @code {example} @endcode: Provides usage examples.

    Backticks ( ): Use for code references.

    @note: Highlights extra notes about the method.

    @brief: Differentiates between brief and detailed explanations.

    @since: Indicates the version in which a function or class was introduced.

    @deprecated: Marks functions or classes as deprecated.

    Paragraphs and Hyperlinks: Use <p> for paragraphs and <a href="..."> for hyperlinks.