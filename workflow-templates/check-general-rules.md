
# "Check General Rules" workflow

Workflow file: [check-general-rules.yml](check-general-rules.yml)

Uses several workflows to check compliance with General Rules of the style guide.

## Readme badge

Markdown badge:

```markdown
[![Check General Rules status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-general-rules.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-general-rules.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

## Commit message

```
ci: Add "Check Check General Rules" verification workflow

On every push or pull request, and periodically (every Tuesday at 8 AM UTC), this workflow checks compliance with the General Rules of the Arduino Library Style Guide. It ensures consistent code styling across the repository.

```