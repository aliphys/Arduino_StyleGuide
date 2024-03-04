# Rule
- Death to Tabs!: The tab character (ASCII 0x09) shall never appear within any source code or sketch file.

# Example
## Good example
```
// Using spaces
void setup() {
    initializeSensors();
    startCommunication();
}
```
## Bad example
```
// Tabs not allowed for indentation
void setup() {
	initializeSensors();
	startCommunication();
}
```

# Reasoning
- Consistency Across Environments: The width of the tab character varies by text editor and programmer preference, leading to inconsistent visual layout. Using spaces ensures a consistent layout across different tools and environments.
- Bug prevention: Since the tab button varies in operation, this can create both unwanted bugs as well as errors in Doxygen parsing.  See → https://www.reddit.com/r/learnpython/comments/wsxpxc/why_should_i_not_use_tabs_over_spaces/