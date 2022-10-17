# Crystal Linux General Contributing Guidelines

### Pre-Commit Checks

- Make sure to format AND lint your code before every commit push
- Always make sure you're on a custom branch, never commit directly to main (Most repositories have protections against doing this). 
  Main is a protected branch and should only be PRed against from other branches once the code is proven to be stable

### Formatting

#### General
- UNIX line endings (LF instead of CRLF)
- Please keep variable names descriptive (e.g., `archive` vs `ar`)

#### Rust
- 4 spaces per indent
- Format code with `cargo fmt` often

#### Python
- 4 spaces per indent
- No sloppy code! I better at LEAST see an `if __name__ == "__main__":` if your code is actually going to run as a script.

#### Nix
- 2 spaces per indent
- Check derivations/flakes with `statix`, `nix-linter` and format with `nixfmt`

### Git

- Please don't leave `Merge ...` commits. They clutter up the git log.
- All development is to take place on `main` from now on. Releases will be handled as versioned Git tags on `main`
- Please follow the [GNOME Git Commit Message Guidelines](https://wiki.gnome.org/Git/CommitMessages)

### Good Practices

- Make sure to annotate what each commit actually changes... `git diff` is your friend.
- Try to use handle all errors if possible.
- Never leave an unhandled exception in production code. If you have found a behaviour that runs an uncaught exception, catch the exception.
- Never use `println!()` or the langauge's default print function/macro in production code. Using prettified string functions (e.g. info() in Amethyst v3.0.0) is
  preferred
- Compartmentalise as much as you can, avoid writing the exact same line of code 50 times if you can turn it into a
  function

### Examples of these guidelines in practice

- [Amethyst](https://github.com/crystal-linux/amethyst)
- [Jade](https://github.com/crystal-linux/jade)
