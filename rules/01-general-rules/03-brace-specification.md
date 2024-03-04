# Rule:
- In Arduino code, braces {} must always surround blocks of code following control statements like if, else, switch, while, do, and for, excluding single statements and empty statements.
- Each left brace { should appear by itself on the same line of the control statement. The corresponding right brace } should appear by itself at the start of the block, the appropriate number of lines later in the file. This is also known as One True Brace style. 

# Example
## Good example
```
if (sensorValue > threshold) {
    digitalWrite(LED_BUILTIN, HIGH);
}
else {
    digitalWrite(LED_BUILTIN, LOW);
}

if (sensorValue > threshold) {
    activateAlarm();
}
// single line statement
if (sensorValue > threshold) activateAlarm();
if (condition);
if (condition) {
    // Intentionally left blank
}
```
## Bad example
```
if (sensorValue > threshold) 
{
    digitalWrite(LED_BUILTIN, HIGH);
}
else 
{
    digitalWrite(LED_BUILTIN, LOW);
}
```

# Reasoning
The One True Brace style increases readablity by specifying the start of code blocks. It is also space efficient, reducing vertical scrolling that can occur when brackets are on a seperate line. Excluding single and empty statements from this rule allows for more concise code, especially for simple conditional actions or intentional no-operations.

# Enforcement
The following clang-format configurations, enforces the brace wrapping
```
CommentPragmas:  '/\*(.+\n.+)+\*/'
ReflowComments: false
BraceWrapping:
  AfterClass:      false
  AfterControlStatement: false   
  AfterEnum:       false
  AfterFunction:   false         
  AfterNamespace:  false
  AfterStruct:     false
  AfterUnion:      false
  AfterExternBlock: false
  BeforeCatch:     false         
  BeforeElse:      true         
  IndentBraces:    false
AllowShortIfStatementsOnASingleLine: true
AllowShortLoopsOnASingleLine: true
AllowShortBlocksOnASingleLine: Always
BreakBeforeBraces: Custom
```