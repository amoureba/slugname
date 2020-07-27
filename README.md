# Bash Command: Slugname

Slugname is a bash command that converts filenames and directories to a web friendly format.

## Usage Help

Simply enter the slugname command without any arguments or with the -h option to view the usage help.

    $ slugname
    usage: slugname [-hnv] source_file ...
       -h: help
       -n: dry run
       -v: verbose

## Usage Examples

Note, most examples below are run in verbose mode (-v) to help illustrate the results.

Verbose mode is unnecessary in real world scenarios.

#### Provide filenames:

    $ slugname -v "UPPER CASE FILE.txt"
    rename: UPPER CASE FILE.txt -> upper-case-file.txt

#### Play it safe with a dry run:

Dry run mode does not alter the filesystem in any way.

    $ slugname -n *
    --- Begin dry run mode.
    rename: My file.txt -> my-file.txt
    ignore: web-friendly-filename.txt
    --- End dry run mode.

Dry run mode also allows you to test filenames that don't exist. Great for testing!

    $ slugname -n "Ghost File.txt"
    --- Begin dry run mode.
    not found: Ghost File.txt
    rename: Ghost File.txt -> ghost-file.txt
    --- End dry run mode.

Dry run mode automatically enables verbose mode so there is no need to include the -v option with -n.
