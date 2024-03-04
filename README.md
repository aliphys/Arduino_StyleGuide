# Arduino_StyleGuide
This repository contains the official Arduino Style guide for library development, building upon the MISRA C: 2012 and [BARR-C:2018](https://barrgroup.com/embedded-systems/books/embedded-c-coding-standard) industrial standards for embedded development.

This repository includes two components.
## `rules`
These are a set of human readable specifications that outline the Style Guide. Each sub rule is defined in a seperate markdown with the following headings.
- **Rules:** Details the rules in a human-readable format
- **Examples:** Provides examples in which case the rule is met or not adhered to
- **Reasoning:** Gives an explanation as to why the specific rule is in place
- **Enforcement:** Specifies how this rule is enforced. This can be via CI tools (such as GitHub Workflows), PR review or a combination.

## `workflow templates`
This directory includes helpful GitHub workflows for automating the enforcement of rules set out in the style guide. Each `.yml` workflow is accompanied by a `.md` file, explaining how to set up the workflow as well as a recommended commit message when appending to the library repository in question.

# Rules

- General Rules
    - [Which C](rules/01-general-rules/01-which-c.md)
    - [Line Width Specification](rules/01-general-rules/02-line-width-specification.md)
    - [Brace Specification](rules/01-general-rules/03-brace-specification.md)
    - [Parantheses](rules/01-general-rules/04-parantheses.md)
    - [Common Abbreviations](rules/01-general-rules/05-common-abbreviations.md)
    - [Cast Specifications](rules/01-general-rules/06-cast-specifications.md)
    - [Keywords to Avoid](rules/01-general-rules/07-keywords-to-avoid.md)
- Comment Rules
    - [Acceptable Formats](rules/02-comment-rules/01-acceptable-formats.md)
    - [Documentation Structure](rules/02-comment-rules/02-documentation-structure.md)
- White Space Rules
    - [Spaces](rules/03-white-space-rules/01-spaces.md)
    - [Blank Lines](rules/03-white-space-rules/02-blank-lines.md)
    - [Indentation](rules/03-white-space-rules/03-indentation.md)
    - [Tabs](rules/03-white-space-rules/04-tabs.md)
    - [Non-Printing Characters](rules/03-white-space-rules/05-non-printing-characters.md)
    - [Alignment](rules/03-white-space-rules/06-alignment.md)
- Module Rules
    - [Naming Conventions](rules/04-module-rules/01-naming-conventions.md)
    - [Header Files](rules/04-module-rules/02-header-files.md)
    - [Source Files](rules/04-module-rules/03-source-files.md)
- Data Type Rules
    - [Naming Conventions](rules/05-data-type-rules/01-naming-conventions.md)
    - [Fixed Width Integers](rules/05-data-type-rules/02-fixed-width-integers.md)
    - [Signed and Unsigned Integers](rules/05-data-type-rules/03-signed-and-unsigned-integers.md)
    - [Floating Point](rules/05-data-type-rules/04-floating-point.md)
- Procedure Rules
    - [Naming Conventions](rules/06-procedure-rules/01-naming-conventions.md)
    - [Functions](rules/06-procedure-rules/02-functions.md)
- Variable Rules
    - [Naming Conventions](rules/07-variable-rules/01-naming-conventions.md)
    - [Initialization](rules/07-variable-rules/02-initialization.md)
- Statement Rules
    - [Variable Declarations](rules/08-statement-rules/01-variable-declarations.md)
    - [Conditional Statements](rules/08-statement-rules/02-conditional-statements.md)
    - [Switch Statements](rules/08-statement-rules/03-switch-statements.md)
    - [Loops](rules/08-statement-rules/04-loops.md)