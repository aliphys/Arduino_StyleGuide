# Rule
- In Arduino code, each cast must be accompanied by a comment explaining why the cast is necessary.

# Examples
## Good Example
```
// cast rational specified
int sensorValue = analogRead(sensorPin);
double voltage = (double)sensorValue / 1023.0; // Cast to double for precision in division
```
## Bad Example
```
// cast rational not specified
int sensorValue = analogRead(sensorPin);
double voltage = (double)sensorValue / 1023.0; // null

int value = 10;
int result = (int)value; // Unnecessary cast: 'value' is already an int
```

# Reasoning
We assume that if the coder will remove the cast, if writing a comment is too troublesome. Rational for the cast, may not be understood by looking directly a the line. And in some cases, can be the results of sub-optimal programming practises. This is especially important in the Arduino community where learners and hobbyists might be unfamiliar with certain casting nuances. Requiring a comment for each cast encourages developers to think about whether a cast is the best solution, potentially preventing bugs and unintended behavior. Furthermore, often the data type changes several times between the hardware to the user. The casting can affect the accuracy and units of the data. Casting performed without a valid or explained reason, can lead to loss of data (like precision in the case of casting from float to int) or simply add unnecessary complexity to the code. These practices are generally not recommended as they can degrade the readability and efficiency of the code. Thus, any casting should be made clear.

# Enforcement
The GitHub workflow will provide a error when casting happens, without a comment on the same line. Use `grep` to identify the offending lines: `(static_cast<.*?>|reinterpret_cast<.*?>|\(.*?\)).*(?<!//.*)`. This does not cover all cases, and manual review in PR is required. 