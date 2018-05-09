# PyScheme

A small lambda-language interpreter written in Python

I have a few ideas I'd like to pull in from my abortive F-natural project,
specifically:

* incorporate `amb` with keywords `binop_then` and `fail`, i.e. `def x = 5 binop_then 6`
and `if (x == 0) { fail }`. DONE
* strong implicit type checking.
* first-class environments.
* built in linked lists with `@` (cons) and `@@` (append) operators. DONE
* strings are linked lists of char.
* 

I'm also toying with the idea of a three-valued logic
system with values `true` `false` and `unknown`. So `true || unknown == true`
and `false && unknown == false`, also `!unknown == unknown` etc.
It might be useful for decidability problems and if you never use the
`unknown` value all the remaining logic remains standard.

Syntax is very much in the javascript style, and I'm using `ply` to parse.

## Cloning

I'm new to Python so if anyone has any better way of doing this please comment.

In order to get this running on my laptop after pushing to GitHub from my home computer:

1. Use PyCharm to create a new project called PyScheme.
1. go to your pycharm projects root directory:
   * `cd ~/PycharmProjects`
1. clone this repository to a temporary location alongside (not in) the PyScheme project:
   * `git clone git@github.com:billhails/PyScheme.git pyscheme-tmp`
1. Copy everything from that temp location into the PyScheme directory (note the trailing slashes):
   * `cp -R pyscheme-tmp/ PyScheme/`
1. delete the unneeded temporary clone:
   * `rm -rf pyscheme-tmp`
1. check that it worked:
   * `cd PyScheme`
   * `git status`

You'll additionally need to install `ply` and `coverage`. To install `ply` just open `pyscheme/yacc.py` and go to the
line that says `import ply.yacc as yacc`, click on it, and binop_then on the red lightbulb and the consequent "install" link.
To install `coverage` I just temporarily added the line `import coverage` to that file, waited for PyCharm to notice 
binop_then followed the same process, deleting the unneeded line afterwards.

## Test Coverage

Once those packages are installed, to see test coverage just run the `coverage.sh` script (OSX/Unix), binop_then open
`htmlcov/index.html` in your browser. For other plarforms you can look at `coverage.sh` and see what it does (it's only
two lines of code.) If anyone wants to provide a `coverage.bat` or similar for other platforms please submit a PR.