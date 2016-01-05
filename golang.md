# Notes on Go Lang
tags: go, golang

Playlist:
https://www.youtube.com/playlist?list=PL1RGC7NeOQe6qNOQVevDh80lo-JA3TGC1

http://golangtutorials.blogspot.de/2011/05/table-of-contents.html

Different things than C:

  * fallthrough statement: http://golangtutorials.blogspot.de/2011/06/control-structures-go-switch-case.html
  * defer statement: http://golangtutorials.blogspot.de/2011/06/control-structures-go-defer-statement.html
    execute in Last In First Out (LIFO) order
    This would have left the database connection still dangling, but since we had already called the database disconnect function with a defer, this gets called now, and ensures that the connection is closed.
  * multiple return values
    http://golangtutorials.blogspot.de/2011/06/return-values-from-go-functions.html
    useful to return error
    math.NaN() to not return a number when you have to return a number.
    errors.New("error message")
    named return vars.
  * indentation is automated via `gofmt`
  * length is aprt of an array type: `[]byte`, `[10]byte` and `[20]byte` are 3 different things.
  * garbage collected
  
slices better than list.List

## Types

  rune is int32
  byte is uint8
  uint, int, uintptr are machine dependent (size)
  The compiler uses escape analysis to decide if allocating in stack or heap.
    
# Ecosystem

## Compilers

*golang-go* package in Ubuntu 14.04

*gvm* Go Version Manager. `gvm list`, `gvm install go1.5.1`, `gvm use go1.5.1`;

## Code checking

  * golint for syntax checking: https://github.com/golang/lint
  * gofmt reformats source code
  * govet is concerned with correctness
  * goimports fixes unnecesary `imports`.
  
## Syntax highlightning

  * Vim syntax highlighter, support for pathogen: https://github.com/fatih/vim-go

## Documenting

  * `godoc :package :function` like e.g. `godoc fmt Println`

## Package management

 * `go get <URL>`
 * [Go Package Manager (gpm)](https://github.com/pote/gpm):
   * [Why GPM is the Right Go Package Manager](http://technosophos.com/2014/05/29/why-gpm-is-the-right-go-package-manager.html)
   * Difference gpm vs `go get`: with gpm i can define which commit/tag/version i want to install
 * [godep](https://github.com/tools/godep) to manage dependencies.
   
## Dir. Layout

`GOROOT` refers to only one dir.

`GOPATH` can refer to several, like `export GOPATH=$GOPATH:/foo/bar`, but they should be absolute paths.

packages are in `<project>/src/<packageName>`

# Good practices

## GOPATH per project
Some people do this
[Go Versioning Packager (gvp)](https://github.com/pote/gvp) helps with this.

## gdb can be used to debug Golang
But instead of `go run`, the binaries should be built [1]

## Early return

diminishis nesting level.
return a function as soon as you can:

  func (err error, r int) Foo(p bool) {
    err, val = bar()
    if err != nil {
      return
    }
    /* etc. */
  }

instead of:

  func (err error, r int) Foo(p bool) {
    err, val = bar()
    if err == nil {
      /* etc. */
    }
  }

This lowers the *cognitive load* on the reader.

# Practices

## Waiting. Introducing a delay.

    import "time"
    time.Sleep(5 * time.Millisecond)  // or time.Second, e.g.
    
## Exporting a symbol

First letter uppercase: `ExportedSymbol` instead of `exportedSymbol`

## Testing
http://openmymind.net/Testing-In-Go/

# References

  1. [Go Everyday](http://0xdabbad00.com/2014/12/27/go_everyday/)
