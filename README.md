[![Build Status](https://travis-ci.org/jpcre2/pcre2.svg?branch=release)](https://travis-ci.org/jpcre2/pcre2)

Disclaimer
----------

1. Version that resembles the official version (10.22 etc ...) are just mere copy of the original source (from links mentioned below).
2. Version that includes minor version string is a modified version of the original. For example, 10.21.01 or such are modifications of 10.21
3. This repository should not be used as the original source for PCRE2, use the official channel instead.
4. If you want to share link to this repository, make sure you clear the fact that it's not the official place to download the PCRE2 source.
5. This repository may or may not keep records of all official PCRE2 releases.

README file for PCRE2 (Perl-compatible regular expression library)
------------------------------------------------------------------

PCRE2 is a re-working of the original PCRE library to provide an entirely new
API. The latest release of PCRE2 is always available in three alternative
formats from:

  ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre2-xxx.tar.gz
  
  ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre2-xxx.tar.bz2
  
  ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre2-xxx.zip

There is a mailing list for discussion about the development of PCRE (both the
original and new APIs) at pcre-dev@exim.org. You can access the archives and
subscribe or manage your subscription here:

   https://lists.exim.org/mailman/listinfo/pcre-dev

Please read the NEWS file if you are upgrading from a previous release.

The PCRE2 APIs
--------------

PCRE2 is written in C, and it has its own API. There are three sets of
functions, one for the 8-bit library, which processes strings of bytes, one for
the 16-bit library, which processes strings of 16-bit values, and one for the
32-bit library, which processes strings of 32-bit values. There are no C++
wrappers.

The distribution does contain a set of C wrapper functions for the 8-bit
library that are based on the POSIX regular expression API (see the pcre2posix
man page). These can be found in a library called libpcre2posix. Note that this
just provides a POSIX calling interface to PCRE2; the regular expressions
themselves still follow Perl syntax and semantics. The POSIX API is restricted,
and does not give full access to all of PCRE2's facilities.

The header file for the POSIX-style functions is called pcre2posix.h. The
official POSIX name is regex.h, but I did not want to risk possible problems
with existing files of that name by distributing it that way. To use PCRE2 with
an existing program that uses the POSIX API, pcre2posix.h will have to be
renamed or pointed at by a link.

If you are using the POSIX interface to PCRE2 and there is already a POSIX
regex library installed on your system, as well as worrying about the regex.h
header file (as mentioned above), you must also take care when linking programs
to ensure that they link with PCRE2's libpcre2posix library. Otherwise they may
pick up the POSIX functions of the same name from the other library.

One way of avoiding this confusion is to compile PCRE2 with the addition of
-Dregcomp=PCRE2regcomp (and similarly for the other POSIX functions) to the
compiler flags (CFLAGS if you are using "configure" -- see below). This has the
effect of renaming the functions so that the names no longer clash. Of course,
you have to do the same thing for your applications, or write them using the
new names.


Documentation for PCRE2
-----------------------

Refer to the README file for details.

