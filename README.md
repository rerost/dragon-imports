# dragon-imports [![Build Status](https://travis-ci.org/monochromegane/dragon-imports.svg?branch=master)](https://travis-ci.org/monochromegane/dragon-imports)

A tool for speedup goimports command :dragon:

## Usage

All you have to do run `dragon-imports` command :+1:

```sh
$ dragon-imports
```

After run the command, your goimports will become fast :dizzy:

**goimports time (sec)**

| before | after |
| ------:| -----:|
| 0.893  | 0.019 |

## How dose it work?

`goimports` command searches for a package with the given symbols from stdlib mappings at first. In this case, the command hopefully never have to scan the GOPATH.

`dragon-imports` add GOPATH's libs to stdlib mappings, and install goimports again.

new `goimports` have stdlib and all GOPATH's libs mappings, it's very fast.

**Note:** It supports `.goimportsignore` and ignores `vendor/` directory.

## Return to the original goimports

You can return to the original goimports by the following:

```sh
$ dragon-imports --restore
```

## Installation

```sh
$ go get github.com/monochromegane/dragon-imports/...
```

**Note:**
  dragon-imports supports golang.org/x/tools older than [the revision](https://github.com/golang/tools/commit/5bbcdc15656ef390fab5dd6e8daf95354f7171e3).
  So, I recommend upgrading golang.org/x/tools by `go get -u golang.org/x/tools/...`.

## ToDo

- File system notification.

## Contribution

1. Fork it
2. Create a feature branch
3. Commit your changes
4. Rebase your local changes against the master branch
5. Run test suite with the `go test ./...` command and confirm that it passes
6. Run `gofmt -s`
7. Create new Pull Request

## License

[MIT](https://github.com/monochromegane/dragon-imports/blob/master/LICENSE)

## Author

[monochromegane](https://github.com/monochromegane)

