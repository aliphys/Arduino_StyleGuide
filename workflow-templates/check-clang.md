# "Check Clang" workflow (private repos)

Workflow file: [check-clang.yml](check-clang.yml)

Uses [`jidicula/clang-format-action`](https://github.com/jidicula/clang-format-action) to parse the sketches using version 17 of the clang-format tool. The [`.clang-format`](.clang-format) configuration file must be located inside the root directory of the library.

This workflow is configured to parse the `src` and `examples` subfolders inside a library. Add additional folders (for example `extras/tests`) to the stratergy matrix. 

**NOTE**: The `git submodule` feature can be used to make a symbolic link with the `.clang-format` file inside this repository.

**NOTE**: The [Microsoft C/C++ extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) can make use of the .clang-format file for source code formatting, when the extension is installed. By default, `Shift+Alt+F` will format the entire docuement and `Ctrl+K Ctrl+F` will format the selection. See the [official documentation](https://code.visualstudio.com/docs/cpp/cpp-ide#_code-formatting) for more information.

## Readme badge

Markdown badge:

```markdown
[![Compile Examples status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-clang.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-clang.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

## Commit message

```
ci: Add "Check Clang" verification workflow

On every push or pull request, and periodically (every Tuesday at 8 AM UTC), this workflow checks the formatting of files using clang-format. It ensures consistent code styling across the repository.

```