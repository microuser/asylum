# Processing Dispatch Layer

## Responsibility

This layer iterates over all user-supplied paths and dispatches the configured actions (cleaning, folderizing) to each path. It uses control structures like `for` loops to ensure all paths are processed.

## Example
```rust
for path in paths {
    if should_clean {
        // Clean files/folders
    }
    if should_folderize {
        // Folderize files
    }
}
```

## Notes
- Ensures every input path is handled according to user configuration.
- Connects high-level user intent to lower-level action execution.
