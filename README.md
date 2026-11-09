# Single-line Section

Compile a single line of Skript code into a section object. The generated section can receive arguments and is compiled in a selected script context.

## Requirements

- Skript 2.15+
- skript-reflect 2.6+
- skript-mirror (the package imports its section and reflection classes)

## Installation

```
package install https://github.com/devdinc/single-line-section
```

## Syntax

```skript
[new] [single] line section %strings% [with arguments %objects%] [in %script%]
```

The code is supplied as a string or list of strings. Optional arguments identify the variables available to the compiled section. The optional script selects the script context used when compiling it; otherwise the current script is used.

## Example

```skript
set {_code::*} to "broadcast ""Hello, %{_name}%"""
set {_section} to line section {_code::*} with arguments {_name}
```

The expression returns a Skript section object. It snapshots the caller's local variables when evaluated and compiles the supplied code as a section; use the returned section with the Skript section API available in your environment.

## Dependencies

This package depends on [scoped-variables](https://github.com/devdinc/scoped-variables) and requires skript-mirror classes.

## Source

- Implementation: `src/single-line-section.sk`
