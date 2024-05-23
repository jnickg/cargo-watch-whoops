# Cargo Watch Bug

Run the following commands:

0. `cargo binstall cargo-watch`
1. `docker compose up -d mongodb`
2. `cargo watch -- cargo run` or just `cargo watch`

## Expected behavior

`cargo watch` should know to ignore the ignored artifacts, per the documentation in `cargo watch --help`, which states:

> `By default, the workspace directories of your project and all local dependencies are watched, except for the target/ and .git/ folders. Your .ignore and .gitignore files are used to filter paths.`

## Actual behavior

Observe the error: `Error: I/O error: Permission denied (os error 13)`, despite `.gitignore` ignoring that directory.

## Notes

Tested with `cargo-watch 8.5.2`
