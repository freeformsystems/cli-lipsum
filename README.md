Table of Contents
=================

* [lipsum(1)](#lipsum1)
  * [Install](#install)
  * [Usage](#usage)
  * [License](#license)

lipsum(1)
=========

Canonical example for the [command](https://github.com/freeformsystems/cli-command) module.

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

When invoked without the -h | --help option the program will print some lorem
ipsum paragraphs.

Usage: lipsum [-jcve] [--json] [--collapse] [--vanilla]
              [--sort=null|false|true|1|-1]
              [--format=text|json|markdown]
              [--align=column|line|flex|wrap] [--maximum=INT]

Options:
 -e, --exit         Include exit section from error definitions.
     --[no]-color   Enable or disable terminal colors.
 -l, --latin        Include mock lipsum options and commands.
 -j, --json         Print help as json.
 -c, --collapse     Collapse whitespace between sections.
 -v, --vanilla      Disable parameter replacement.
     --debug        Enable debugging.
 -s, --sort=[value] Alters the help option sort order. Set to null to use
                    natural order which is likely the order that options were
                    declared in however this is not guaranteed. Use false for
                    the default sorting logic which favours options with more
                    names, use true to sort lexicographically
                    (Array.prototype.sort). Use 1 to sort by option string
                    length (determined by the length of the help option string),
                    reverse the order with -1.
 -f, --format=[value]
                    Set the help output format.
 -a, --align=[value]
                    Alignment style (column|line|flex|wrap).
 -m, --maximum=[value]
                    Maximum column width, default 80.
 -h, --help         Display this help and exit.
     --version      Output version information and exit.

Examples:
 lipsum --help      Print help using the command module defaults.
 lipsum -lh         Print help and include mock latin options and commands.
 lipsum -jh         Print help as JSON.
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

Report bugs to muji <noop@xpm.io>.
```

## License

Everything is [MIT](http://en.wikipedia.org/wiki/MIT_License). Read the [license](https://github.com/freeformsystems/cli-lipsum/blob/master/LICENSE) if you feel inclined.

This program was built using the [command](https://github.com/freeformsystems/cli-command) module, if you care for excellent documentation and write command line interfaces you should check it out.

Generated by [mdp(1)](https://github.com/freeformsystems/mdp).

[command]: https://github.com/freeformsystems/cli-command
