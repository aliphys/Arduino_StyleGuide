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
```
name: Line Length Checker

on: [push, pull_request]

jobs:
  check-line-length:
    runs-on: ubuntu-latest
    steps:
    - name: Check out code
      uses: actions/checkout@v2

    - name: Install Line Length Checker
      run: sudo apt-get install -y moreutils

    - name: Check Line Length
      run: |
        ! find . -name '*.ino' -o -name '*.h' -o -name '*.cpp' | xargs grep -E '.{121,}' | grep -v '^Binary file'
        if [ $? -eq 0 ]; then
          echo "Lines exceeding 120 characters found!"
          exit 1
        fi
      shell: bash

    - name: Check Soft Line Length Limit
      run: |
        count=$(find . -name '*.ino' -o -name '*.h' -o -name '*.cpp' | xargs grep -E '.{101,}' | grep -v '^Binary file' | wc -l)
        if [ $count -gt 0 ]; then
          echo "Warning: $count lines exceed the soft limit of 100 characters."
        fi
      shell: bash

```

```
name: Clang-Format Line Length Check

on: [push, pull_request]

jobs:
  line-length-check:
    runs-on: ubuntu-latest
    steps:
    - name: Check out code
      uses: actions/checkout@v2

    - name: Install Clang-Format
      run: sudo apt-get install -y clang-format

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

```
name: Auto-fix Line Length and Create PR

on: [push, pull_request]

jobs:
  auto-fix-line-length:
    runs-on: ubuntu-latest
    steps:
    - name: Check out code
      uses: actions/checkout@v2

    - name: Set up Git
      run: |
        git config --global user.name 'Auto Formatter'
        git config --global user.email 'auto-formatter@example.com'

    - name: Install Clang-Format
      run: sudo apt-get install -y clang-format

    - name: Fix Line Length and Create Commit
      run: |
        find . -name '*.cpp' -o -name '*.h' -o -name '*.ino' -exec clang-format -i -style="{ColumnLimit: 120}" {} \;
        git commit -am "Auto-fix line lengths" || echo "No changes to commit"

    - name: Create Pull Request
      uses: peter-evans/create-pull-request@v3
      with:
        token: ${{ secrets.GITHUB_TOKEN }}
        commit-message: Auto-fix line lengths
        title: '[AUTO-FIX] Line Length Fixes'
        body: 'This is an auto-generated PR with fixes for line length issues.'
        branch: auto-fix-line-lengths
        delete-branch: true

```