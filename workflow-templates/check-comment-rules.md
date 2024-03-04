
# "Check Comment Rules" workflow

Workflow file: [check-comment-rules.yml](check-comment-rules.yml)

Uses several workflows to check compliance with Comment Rules of the style guide.

## Readme badge

Markdown badge:

```markdown
[![Check Comment Rules status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-comment-rules.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-comment-rules.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

## Commit message

```
ci: Add "Check Check Comment Rules" verification workflow

On every push or pull request, and periodically (every Tuesday at 8 AM UTC), this workflow checks compliance with the Comment Rules of the Arduino Library Style Guide. It ensures consistent code styling across the repository.

```