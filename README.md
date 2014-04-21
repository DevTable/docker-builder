bob
===

[![Build Status](https://travis-ci.org/rafecolton/bob.svg?branch=master)](https://travis-ci.org/rafecolton/bob)
[![GoDoc](https://godoc.org/github.com/rafecolton/bob?status.png)](https://godoc.org/github.com/rafecolton/bob)

builds a docker image from an arbitrary file

**TODO:** the actual docker image building

## Hacking

```bash
> brew install libgit2 --HEAD # you may need to do this on mac
> make help
# Usage: make [target]
#
# Options:
#
#   help/default: display this message
#
#   all: clean build test
#
#   quick: build + invokes builder a couple times (good for debugging)
#
#   build: gvm linkthis plus installing libs plus installing deps
#
#   test: build fmtpolice and ginkgotests
#
#   dev: set up the dev tool chain
```

## Building

```bash
> builder -h/--help
# Usage:
#   builder [OPTIONS]
#
# Application Options:
#   -v                 Print version and exit
#       --version      Print long version and exit
#       --branch       Print branch and exit
#       --rev          Print revision and exit
#   -q, --quiet        Produce no output, only exit codes (false)
#   -l, --lint=        Lint the provided file. Compatible with -q/--quiet
#   -f, --builderfile= The configuration file for Builder
#
# Help Options:
#   -h, --help         Show this help message
```

## Why?

* base layers
* can only add in one "Dockerfile"
* can't easily exclude dirs / long file names (aufs limitation?)
* generally make it more efficient to build in smaller layers to make
  pushing and pulling faster, etc
