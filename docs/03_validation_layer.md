# Validation Layer

## Responsibility

This layer checks that the user has provided all required arguments and specified at least one action (clean or folderize). If requirements are not met, it provides error feedback and exits early.

## Example
```rust
let should_clean = cli_args.occurrences_of("no-clean") == 0;
let should_folderize = cli_args.occurrences_of("folderize") > 0;

if (!should_clean) && (!should_folderize) {
    behaviors.print_error("Missing action to perform. See --help");
    std::process::exit(1);
}
```

## Notes
- Prevents the program from running without meaningful work.
- Improves user experience by catching errors early.
