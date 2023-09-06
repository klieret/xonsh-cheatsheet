# Minimal xonsh cheat sheet

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/klieret/xonsh-cheatsheet-minimal/main.svg)](https://results.pre-commit.ci/latest/github/klieret/xonsh-cheatsheet-minimal/main)
[![Check Markdown links](https://github.com/klieret/xonsh-cheatsheet-minimal/actions/workflows/check-links.yaml/badge.svg)](https://github.com/klieret/xonsh-cheatsheet-minimal/actions/workflows/check-links.yaml)
 [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com)

Cheat sheet for [xonsh].
For a longer cheat sheet, take a look at [anki-code's version](https://github.com/anki-code/xonsh-cheatsheet).

[xonsh]: https://xon.sh/

## Useful links

* [Official tutorial](https://xon.sh/tutorial.html)
* [Longer cheat sheet](https://github.com/anki-code/xonsh-cheatsheet)

## Notation

* ![py] Works in python mode
* ![sh] Works in subprocess mode
* ![pysh] Works in both modes

## Basics


* ![sh] Evaluate python: `@(python_var)`, `@(1+1)`
* ![py] Capture output of bash command as string: `$(ls)`
    * Same but silent: `$[ls]`
* ![py] Environment variables:
    * Environment variable: `$HOME`
    * All environment variables: `${...}`
    * Environment variable from python expression: `${'HO'+'ME'}`
* ![py] Run bash command and return `CommandPipeline` object: `!(ls)`
    * Same but silent: `![ls]`
* ![pysh] Globbing: ``g`a*b*` `` lists all filenames (`str`) that match `a*b*` in the working directory
* ![py] Using [`pathlib`][pathlib]:
    * `p"/this/is/a/path/"` is a `Path`
    * Globbing: `` p`*.pt` `` returns list of `Path`s

## Scripting

* ![py] Settings:
    * `$XONSH_SHOW_TRACEBACK = True`: Show verbose traceback
    * `$RAISE_SUBPROC_ERROR = True`: Raise error if subprocess fails (e.g., `$(doesntexist)`)
* ![pysh] Command line arguments:
    * Command line argument: `$ARG<n>` (e.g., `$ARG1`)
    * ![py] All arguments as list: `$ARGS`

[pathlib]: https://docs.python.org/3/library/pathlib.html
[sh]: readme_assets/sh.svg
[py]: readme_assets/py.svg
[pysh]: readme_assets/pysh.svg
