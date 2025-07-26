# Command-Line Parsing Layer

## Responsibility

This layer is responsible for defining and parsing all command-line arguments using the `clap` crate. It converts raw user input into a structured form (`clap::ArgMatches`) that the rest of the application can use.

## Example
```rust
let cli_args : clap::ArgMatches = App::new("Asylum")
    .version("1.0")
    .author("Microuser <microuser@users.noreply.github.com>")
    .about("Sanitizes files and folders names")
    .arg(Arg::with_name("path")...)
    .arg(Arg::with_name("no-clean")...)
    .arg(Arg::with_name("folderize")...)
    // ... more arguments ...
    .get_matches();
```

## Notes
- Ensures all user input is validated and available for further processing.
- Provides help and usage information automatically.
