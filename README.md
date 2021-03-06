DBD::Firebird version 1.15
==========================

DBI driver for the Firebird RDBMS server.

- Copyright © 2010-2013  Popa Adrian Marius
- Copyright © 2011-2013  Stefan Suciu
- Copyright © 2011-2013  Damyan Ivanov
- Copyright © 2011  Alexandr Ciornii
- Copyright © 2010-2011  pilcrow
- Copyright © 1999-2005  Edwin Pratomo
- Portions Copyright © 2001-2005  Daniel Ritz

License
-------

You may distribute under the terms of either the GNU General Public
License or the Artistic License, as specified in the Perl README file.
(http://dev.perl.org/licenses/artistic.html)


Installation
------------

Requirements:

- Perl (Threaded and version 5.8.1 or higher)
- Perl DBI (1.41 or higher)
- Firebird (2.5.1 or higher)
- A C compiler
  * UN*X
    GCC 4.x (tested, older may or may not work) or other capable
    clang

  * Windows
    - Strawberry perl (http://strawberryperl.com/) comes with it's own compiler (mingw)
    - or Microsoft Express VC++ 9 (2008) /10 (2010) /11
    - Cygwin
  * Freebsd
    - Threaded Perl is required (You have to re-install Perl from
    ports and you have to select the config option that says 'build a
    Perl with threads')


*BEFORE* BUILDING, TESTING AND INSTALLING this you will need to:

- Build, test and install Perl 5 (at least 5.8.1).
  It is very important to TEST it and INSTALL it!

- Build, test and install the DBI module (at least DBI 1.41).
  It is very important to TEST it and INSTALL it!
  On Debian/Ubuntu you can do a simple:
    sudo apt-get install firebird2.5-dev libdbi-perl

- Remember to *read* the DBI README file if you installed it from source

- Make sure that Firebird server is running (for testing telnet localhost 3050)


BUILDING:
  Win32/Win64 with Strawberry
    type 'dmake' from the console

  Win32/Win64 with MS compiler:
    type 'nmake', not just 'make'

  To Configure and build the DBD:
    perl Makefile.PL
    make

TESTING
  To run tests module Test::Exception is required on Debian/Ubuntu systems:
     sudo apt-get install libtest-exception-perl

  Please, set at least DBI_PASS (or ISC_PASSWORD), before 'make test'.
  The default for DBI_USER is 'SYSDBA'.(masterkey password is given here as example only)
    ISC_PASSWORD=masterkey make test

INSTALLING:
    make install               (if the tests look okay)
