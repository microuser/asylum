# Asylum
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Clean up file and folder names for cross-platform support (NTFS, SMB, Windows, Mac, Linux).

## Overview
Asylum is a command-line tool designed to sanitize and organize file and folder names, ensuring compatibility across different operating systems and filesystems. It provides robust options for cleaning illegal characters, normalizing names, and organizing files into folders.

## Architecture Summary
- **Command-Line Parsing Layer:** Handles all user input and options using the `clap` crate.
- **Behavior Configuration Layer:** Centralizes runtime configuration based on user arguments.
- **Validation Layer:** Ensures required actions and paths are specified, with clear error reporting.
- **Processing Dispatch Layer:** Iterates over user-supplied paths, dispatching the chosen actions.
- **Action Execution Layer:** Applies cleaning or folderizing logic to files and folders using visitor patterns.

For detailed explanations, see the `Documentation/` folder:
- `01_command_line_parsing.md` https://github.com/microuser/asylum/blob/ca02111c8b8d6e62d0c4dab331c5b3f375aabccf/docs/01_command_line_parsing.md
- `02_behavior_configuration.md` docs/02_behavior_configuration.md
- `03_validation_layer.md`
- `04_processing_dispatch.md`
- `05_action_execution.md`

## Example Use Cases

### 1. Clean the `~/Videos` folder (default cleaning)
```sh
asylum --path ~/Videos
```

### 2. Clean and folderize all files in `~/Videos`
```sh
asylum --path ~/Videos --folderize
```

### 3. Dry run (see what would change, but don’t modify files)
```sh
asylum --path ~/Videos --dryrun
```

### 5. Run with Cargo, enable color, folderize, and clean
```sh
cargo run --release  -- --path ~/Videos --color --folderize --clean
```
This command runs Asylum from source, cleans and folderizes all files in `~/Videos`, and enables colored output.


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
