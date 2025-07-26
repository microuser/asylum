# Action Execution Layer

## Responsibility

This layer performs the actual work on files and folders, applying cleaning or folderizing logic via callback functions. It uses visitor patterns to traverse directories and files, applying the appropriate action to each item.

## Example
```rust
visit_dirs_sorted(
    &path.to_path_buf(),
    &|file_or_dir| {
        strip_unwanted_file_or_folder(file_or_dir, &behaviors);
    },
    &behaviors
);

visit_files_sorted(
    &path.to_path_buf(),
    &|file_or_dir| {
        move_file_into_same_named_folder(file_or_dir, &behaviors);
    },
    &behaviors
);
```

## Notes
- Uses callback-based recursion for extensibility.
- Isolates the logic for each action, improving code clarity and maintainability.
