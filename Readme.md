# ASCII-Art-Reverse

ASCII-Art-Reverse is a Go CLI project that converts ASCII art back into normal text.

It follows the original ASCII-art project flow, but in reverse mode it reads an ASCII-art file and decodes it.

## Usage

Reverse mode:

```bash
go run . --reverse=<fileName>
```

Example:

```bash
go run . --reverse=file.txt
```

Invalid reverse flag formats print:

```text
Usage: go run . [OPTION]

EX: go run . --reverse=<fileName>
```

The program is still compatible with previously implemented options and with single `[STRING]` mode.

## Example

Given `file.txt` containing ASCII art for `hello`:

```bash
go run . --reverse=file.txt
```

Output:

```text
hello
```

## Optional Compatibility

This repository also keeps compatibility with existing optional features when correctly formatted:
- `--color=<color>`
- `--out=<file.txt>`
- `--output=<file.txt>`
- `--font=<banner>`
- `--align=<type>`
- `--reverse=<fileName>`

## Project Structure

- `main.go`: entry point
- `pipeline/pipeline.go`: main run orchestration (normal + reverse mode)
- `pipeline/args.go`: CLI argument parsing and validation
- `pipeline/reverse.go`: ASCII-art-to-text reverse decoding logic
- `pipeline/alignment.go`: alignment utilities for normal rendering mode
- `pipeline/loadBanner.go`: banner loading
- `pipeline/tokenize.go`: tokenization
- `pipeline/renderLines.go`: ASCII-art rendering
- `pipeline/colorFormating.go`: color support
- `pipeline/validateInput.go`: input validation
- `pipeline/writeOutput.go`: output writing
- `tests/reverse_test.go`: reverse mode tests
- `tests/args_test.go`: argument parsing tests
- `tests/`: additional unit tests

## Testing

Run all tests:

```bash
go test ./...
```

## Allowed Packages

Only Go standard library packages are used.
