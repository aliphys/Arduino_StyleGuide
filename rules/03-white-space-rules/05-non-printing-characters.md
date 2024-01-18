# Rule
- Line Endings: Source code lines in Arduino projects should end only with the single character ‘LF’ (Line Feed, ASCII 0x0A), not with the pair ‘CR’-‘LF’ (Carriage Return-Line Feed, 0x0D 0x0A).
- Permitted Non-Printable Character: The only other non-printable character permitted in a source code file is the form feed character ‘FF’ (ASCII 0x0C).

# Example
- Configure text editors and IDEs to use 'LF' for line endings instead of 'CR'-'LF'.

# Reasoning
- Cross-Platform Compatibility: Using ‘LF’ for line endings enhances compatibility across different platforms, including Unix-like systems where the ‘CR’-‘LF’ combination can cause issues, especially with multi-line preprocessor macros.
- Consistency in Codebase: Consistent use of non-printing characters prevents issues related to version control and differences in text editor configurations.