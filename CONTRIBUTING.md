# Crystal Linux General Contributing Guidelines

### !! Always make sure to `git pull` before doing any work to avoid commit hell !!

### Pre-Commit Checks

- Make sure to format AND lint your code before every commit push
- Always make sure you're either on a `development` or a custom branch, never commit directly to main.
  Main is a protected branch and should only be PRed against from development once the code is proven
  to be stable

### Formatting

#### General
- UNIX line endings (LF instead of CRLF)

#### Rust
- 4 spaces per indent
- Format code with `cargo fmt` often

#### Python
- 4 spaces per indent
- No sloppy code! I better at LEAST see an `if __name__ == "__main__":` if your code is actually going to run as a script.

#### Nix
- 2 spaces per indent
- Check derivations/flakes with `statix`, `nix-linter` and format with `nixfmt`

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
