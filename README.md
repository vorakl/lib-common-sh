# [Vorakl's Bash library](https://bash.libs.cf/)

[![build-statu](https://travis-ci.org/vorakl/bash-libs.svg?branch=master)](https://travis-ci.org/vorakl/bash-libs)

## Introduction

Bash is a powerful programming language and very useful for operational tasks.
Without any doubts, this is the first "tool" for any system administrators of
Unix-like OS's. Although, non-trivial tasks require non-trivial knowledge, and
sometimes it needs more attention on a language specifics than on solving a task
itself. Unfortunately, Bash doesn't have some sort of a "Standard library" with
all that functions which make a development process easier, faster and more
efficient in all senses.

Suddenly, I realized that I iconstantly use the same functions, same blocks of
code everywhere, and as copy-pasting them from one script to another is not
the right approach, I decided to organize the most used functions in a modules
under one library and place them on a publicly available resource over http.
This makes possible to download them using simple tools or even a pure Bash,
always have the latest version of each module or even get stuck to a specific
version if a reproducibility is needed.

This library aims to minimize the complexity of Bash programming by abstracting
special cases, tricky syntax, and commonly used operations behind functions with
a clear interface and intuitive behavior. All modules can be safely embedded in
other's code as all internal names are namespaced by a unique prefix per each
module. 

Basically, for me using these modules help to

1. reuse the same code everywhere which is checked and proved by the time
2. simplify and speed up a development
3. increase code readability


## Modules

* [sys](https://github.com/vorakl/bash-libs/tree/master/src.docs/content/pages/sys.rst)
* [str](https://github.com/vorakl/bash-libs/tree/master/src.docs/content/pages/str.rst)
* exec
* matrix

All current versions are stored in [latest.lst](http://bash.libs.cf/latest.lst).
It makes it easy to check the latest versions right from the code, like

```bash
#!/bin/bash

lib_versions() (
    source <(curl -sSLf http://bash.libs.cf/latest.lst)
    for m in sys str exec matrix; do
        eval echo "$m: \$$m"
    done
)

lib_versions
```

## Other documentation

* Get started
* [Examples](https://github.com/vorakl/bash-libs/tree/master/examples)
* Installation
* Modification of a default configuration
