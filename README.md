Table of Contents
=================

* [lipsum(1)](#lipsum1)
  * [Install](#install)
  * [Usage](#usage)
  * [Definition](#definition)
* [<pre><code>lipsum](#precodelipsum)
  * [Commands](#commands)
  * [Options](#options)
  * [Examples](#examples)
  * [Copyright](#copyright)
  * [License](#license)

lipsum(1)
=========

Canonical example for the [command](https://github.com/freeformsystems/cli-command) module.

```markdown
## header
```

## Install

```
npm i -g cli-lipsum
```

## Usage

```
Lipsum is a program used to generate lorem ipsum text and to test help output
for the command module.

If the -l | --latin option is specified and it looks like latin then it does
nothing, other more meaningful options that have an affect are interspersed, try
--align and --format in particular. The examples are valid, they illustrate some
of the functionality of the command module.

When invoked without no arguments the program will print some lorem ipsum
paragraphs.

Usage: lipsum <command> [-ljcveh] [--color|--no-color]
              [--debug] [-l|--latin] [-j|--json] [-c|--collapse]
              [-v|--vanilla] [-e|--exit] [-h|--help] [--version]
              [--log-level=<level>] [--log-file=<file>]
              [-s|--sort=(null|true|false|1|-1)]
              [-f|--format=(text|json|markdown)]
              [-a|--align=(column|line|flex|wrap)]
              [-m|--maximum=<60-240>] <args>

Options:

Command should be one of: print, ex.

Commands:
 print              Print some messages using the log middleware.
 ex, exception, e   Throw an exception.

Arguments:
 -v, --vanilla      Disable parameter replacement.
     --[no]-color   Enable or disable terminal colors.
     --log-file=[file]
                    Redirect to log file.
     --debug        Enable debugging.
 -l, --latin        Include mock lipsum options and commands.
 -j, --json         Print help as json.
 -c, --collapse     Collapse whitespace between sections.
     --log-level=[level]
                    Set the log level.
 -e, --exit         Include exit section from error definitions.
 -s, --sort=[value] Alters the help option sort order. Set to null to use
                    natural order which is likely the order that options were
                    declared in however this is not guaranteed. Use false for
                    the default sorting logic which favours options with more
                    names, use true to sort lexicographically using
                    Array.prototype.sort. Use 1 to sort by option string length
                    (determined by the length of the help option string),
                    reverse the order with -1.
 -f, --format=[value]
                    Set the help output format.
 -a, --align=[value]
                    Alignment style.
 -m, --maximum=[value]
                    Maximum column width.
 -h, --help         Display this help and exit.
     --version      Output version information and exit.

Examples:
 lipsum --help      Print help using the command module defaults.
 lipsum -lh         Print help and include mock latin options and commands.
 lipsum -jh         Print help as JSON.
 lipsum -eh         Include exit codes in the help output.
 lipsum --format markdown --help
                    Print help as markdown.
 lipsum -h --align flex
                    Switch to flex alignment.
 lipsum -lh --maximum 100
                    Increase maximum column width.
 lipsum -lh --sort null
                    Disable help option sort (natural order).
 lipsum -lh --sort false
                    Use default sort order.
 lipsum -lh --sort true
                    Use lexicographic sort order.
 lipsum -lh --sort 1
                    Sort by length of option (longest first).
 lipsum -lh --sort -1
                    Sort by length of option (shortest first).
 lipsum --help --no-color
                    Disable terminal colors.
 lipsum --help > help.txt && cat help.txt
                    Verify ANSI escape sequences are not written to files.
 lipsum print       Print some messages, illustrates the log middleware.
 lipsum print --log-level=warn --no-color
                    Set log level to warn and print some messages.
 lipsum ex          Print an error, will be treated as an uncaught exception.
 lipsum ex --debug  Include stack trace in exception and set log level to trace.
 lipsum ex; echo $?;
                    Verify exit code for uncaught exception, compare to `lipsum
                    -eh`.

Report bugs to muji <noop@xpm.io>.
```

## Definition

This program was configured using the following markdown configuration, see [lipsum.md](https://github.com/freeformsystems/cli-lipsum/blob/master/lib/lipsum.md):

<pre><code>lipsum
=================

Lipsum is a program used to generate lorem ipsum text and to test help output for the command module.

If the -l | --latin option is specified and it looks like latin then it does nothing, other more meaningful options that have an affect are interspersed, try --align and --format in particular. The examples are valid, they illustrate some of the functionality of the command module.

When invoked without no arguments the program will print some lorem ipsum paragraphs.

## Commands

* `print`: Print some messages using the log middleware.
* `ex, exception, e`: Throw an exception.

## Options

* `-l, --latin`: Include mock lipsum options and commands.
* `-j, --json`: Print help as json.
* `-c, --collapse`: Collapse whitespace between sections.
* `-v, --vanilla`: Disable parameter replacement.
* `-e, --exit`: Include exit section from error definitions.
* `-s, --sort [value]`: Alters the help option sort order. Set to null to use natural order which is likely the order that options were declared in however this is not guaranteed. Use false for the default sorting logic which favours options with more names, use true to sort lexicographically using *Array.prototype.sort*. Use 1 to sort by option string length (determined by the length of the help option string), reverse the order with -1.
* `-f, --format [value]`: Set the help output format.
* `-a, --align [value]`: Alignment style.
* `-m, --maximum [value]`: Maximum column width.

## Examples

Print help using the command module defaults:

```
lipsum --help
```

Print help and include mock latin options and commands:

```
lipsum -lh
```

Print help as JSON:

```
lipsum -jh
```

Include exit codes in the help output:

```
lipsum -eh
```

Print help as markdown:

```
lipsum --format markdown --help
```

Switch to flex alignment:

```
lipsum -h --align flex
```

Increase maximum column width:

```
lipsum -lh --maximum 100
```

Disable help option sort (natural order):

```
lipsum -lh --sort null
```

Use default sort order:

```
lipsum -lh --sort false
```

Use lexicographic sort order:

```
lipsum -lh --sort true
```

Sort by length of option (longest first):

```
lipsum -lh --sort 1
```

Sort by length of option (shortest first):

```
lipsum -lh --sort -1
```

Disable terminal colors:

```
lipsum --help --no-color
```

Verify ANSI escape sequences are not written to files:

```
lipsum --help > help.txt && cat help.txt
```

Print some messages, illustrates the log middleware:

```
lipsum print
```

Set log level to warn and print some messages:

```
lipsum print --log-level=warn --no-color
```

Print an error, will be treated as an uncaught exception:

```
lipsum ex
```

Include stack trace in exception and set log level to trace:

```
lipsum ex --debug
```

Verify exit code for uncaught exception, compare to `lipsum -eh`:

```
lipsum ex; echo $?;
```

## Copyright

Copyright (C) 2014 Freeform Systems, Ltd.
This is free software; see the source for copying conditions. There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.</code></pre>

## License

Everything is [MIT](http://en.wikipedia.org/wiki/MIT_License). Read the [license](https://github.com/freeformsystems/cli-lipsum/blob/master/LICENSE) if you feel inclined.

This program was built using the [command](https://github.com/freeformsystems/cli-command) module, if you care for excellent documentation and write command line interfaces you should check it out.

Generated by [mdp(1)](https://github.com/freeformsystems/mdp).

[command]: https://github.com/freeformsystems/cli-command
