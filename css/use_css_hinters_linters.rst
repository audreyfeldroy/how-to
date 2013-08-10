==================================
How to Use CSS Hinters and Linters
==================================

CSS hinters and linters help you find and fix problems with your CSS.

Installation
------------

Install the linters that you want::

    $ npm install csslint -g
    $ npm install prettycss -g
    $ [sudo] npm install recess -g

Recess
------

Run Recess to find some problems::

    $ recess project/assets/css/example.css 

    Analyzing the following files: project/assets/css/example.css

    FILE: project/assets/css/example.css
    STATUS: Busted
    FAILURES: 1 failure

    Incorrect property order for rule ".someclass"

      Correct order below:

          12.  position: fixed;
          13.  top: 3em;
          14.  right: 4em;

I can't find built docs on the set of rules that Recess uses, but if you look
at the docstrings in https://github.com/twitter/recess/tree/master/lib/lint,
they're described there.

CSSLint
-------

Run CSSLint to find other problems::

    $ csslint project/assets/css/example.css 

    csslint: There are 1 problems in project/assets/css/example.css.

    example.css
    1: warning at line 18, col 3
    Fallback color (hex or RGB) should precede RGBA color.
      color: rgba(255,255,255,0.5);

CSSLint rules: https://github.com/stubbornella/csslint/wiki/Rules

PrettyCSS
---------

Run PrettyCSS to find even more problems::

    $ prettycss project/assets/css/example.css 
    There were 0 errors and 2 warnings detected.
    Warning:  You should use a relative unit instead of px (1px, line 22, char 16)
    Warning:  You should use a relative unit instead of px (-1px, line 22, char 20)

PrettyCSS error/warning reference: https://github.com/fidian/PrettyCSS/blob/master/docs/ErrorsAndWarnings.md

Makefiles and Linters
---------------------

You can use a Makefile to run several linters with one command.

Create a file called `Makefile` that contains this::

    lint:
      	recess project/assets/css/example.css
      	csslint project/assets/css/example.css
      	prettycss project/assets/css/example.css

.. warning:: Use tabs in `Makefile`, not spaces! Spaces don't work.
   `Makefiles` are the only place in any project where tabs are okay.

What Next?
----------

Here are some suggestions on what to do next.

* Configure the linters to ignore certain rules, if you want.
* Set up Grunt tasks to run the linters. See http://gruntjs.com
