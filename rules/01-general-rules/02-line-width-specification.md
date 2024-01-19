# Rule
- In Arduino code, including examples sketches (.ino) and source files (.h/.cpp), the width of all lines must be maximum of 120 characters.
  - 100 characters is set as a soft limit
- .md files are excluded from this rule

# Example
## Good Example
```
// Under 100 characters
int result = calculateSum(15, 20, 35, 40);
// Improved Example by breaking line
int result = calculateSumWithAdditionalProcessing(15, 20, 35, 42, 100,
                                                  someVariable,
                                                  someOtherVariable,
                                                  yetAnotherVariable);
```

## Bad Example
```
// Exceeds 120 characters
int result = calculateSumWithAdditionalProcessing(15, 20, 35, 42, 100, someVariable, someOtherVariable, yetAnotherVariable);

```

# Reasoning
Shorter lines are generally easier to read and understand. When code is kept within a reasonable line length, it prevents the need for horizontal scrolling, which can disrupt the flow of reading and comprehension. Furthermore, the Git version system is line-based: shorter lines are therefore more desireable for code reviews, pull requests and merging. A decision has to be made, 120 characters is set as the hard upper limit to provide the most leniency at the same time. Given that Markdown files are designed to primarily convey information - not code - they are excluded from the line limit restrictions.

# Enforcement
- Use `clang-format` tool to give error if line is above 120 lines
- ```
    - name: Check Line Length
      run: |
        find . -name '*.cpp' -o -name '*.h' -o -name '*.ino' | while read file; do
          clang-format -style="{ColumnLimit: 120}" "$file" | diff "$file" -
          if [ $? -ne 0 ]; then
            echo "File $file does not meet the line length requirement."
            exit 1
          fi
        done
  ```