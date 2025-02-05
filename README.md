# YAMLFMT

[![GitMoji](https://img.shields.io/badge/Gitmoji-%F0%9F%8E%A8%20-FFDD67.svg)](https://gitmoji.dev)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![Lines Of Code](https://img.shields.io/tokei/lines/github.com/UltiRequiem/yamlfmt?color=blue&label=Total%20Lines)
![CodeQL](https://github.com/UltiRequiem/yamlfmt/workflows/CodeQL/badge.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/UltiRequiem/yamlfmt)](https://goreportcard.com/report/github.com/UltiRequiem/yamlfmt)

A simple and extensible [yaml](https://yaml.org) formatter.

## Installation

```bash
go install github.com/UltiRequiem/yamlfmt@latest
```

Make sure your `$PATH` includes the `$GOPATH/bin` so this command can be used anywhere.

You can also use the binaries from
[releases](https://github.com/UltiRequiem/yamlfmt/releases).

## Usage

- To format one or more files and write to stdout:

  ```bash
  yamlfmt a.yaml b.yaml c.yaml
  ```

- To format one or more files in the replace mode:

  ```bash
  yamlfmt -w a.yaml b.yaml c.yaml
  ```

  If you want to log the files that have been formatted, you can use the `-l` flag also.

- To format stdin and write to stdout:

  ```bash
  cat a.yaml | yamlfmt
  ```

- To format stdin and write to a file:

  ```bash
  cat a.yaml | yamlfmt > b.yaml
  ```

- To format every file in your current directory and subdirectorys:

  - Using `find`:

    ```bash
    yamlfmt -w $(find -name "*.yaml")
    ```

  - Using `fd`:

    ```bash
    yamlfmt -w $(fd -H -e yaml)
    ```

### Editor Integration

- Neovim / Vim

Put this somewhere in your configuration:

```viml
au FileType yaml let &l:formatprg= "yamlfmt /dev/stdin"
```

It can Probably integrate with others editors easily but I only use Neovim.
If you know how to integrate it with some other editor,
please open a pull requests or issue with the information.

#### License

This project is licensed under the [MIT license](./LICENSE.md).
