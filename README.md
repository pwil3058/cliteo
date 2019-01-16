# cliteo - Command Line Interface Test Expected Output

cliteo is a Python script for testing command line interfaces (CLI) by
evaluating scripts that describe the test. Test scripts are simple text
files specifting commands to be run and the expected output.

Lines that begin with a "$" are interpreted as a command to be run.
Lines that begin with a "<" are interpreted as input for the command.
Lines that begin with a ">" are interpreted as the expected output on
the commands stdout.
Lines that begin with a "!" are interpreted as the expected output on
the commands stderr.
Lines that begin with a "?" are expected to contain an integer that is
the expected return value for the command.
All other lines are treated as comments and are ignored.

For example,

$ ls .
? 0
> cliteo
> LICENSE
> README.md

turns this file into a test script which cliteo can evaluate.

Usage:

usage: cliteo [-h] [-q] [-v] [-t] script

Run and evaluate a test script.

positional arguments:
  script         name of the file containing the script to be run.

optional arguments:
  -h, --help     show this help message and exit
  -q, --quiet    operate in quiet mode.
  -v, --verbose  operate in verbose mode.
  -t, --tempdir  run the test script in a clean temporary directory.
