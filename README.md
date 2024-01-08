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
