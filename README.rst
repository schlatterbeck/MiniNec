MiniNec
=======

BASIC source code and DOS executable for mininec3 from NOSC (Naval
Ocean Systems Command)

.. |-| unicode:: U+202F .. Thin non-breaking space
    :trim:

Note that I've written a version of MININEC in Python, pymininec_, so
I'm using this version of the Basic code mainly for regression testing
of my Python version. The Python version is *much* faster because it
uses numpy_ vectorization.

This has the following changes to the original:

- Larger data structures for larger models (see the DIM statements in
  the beginning)
- Elliptic integral and gaussian quadrature constants with corrections
  and better accuracy see README of pymininec_ for details on the
  corrections of elliptic integral parameters
- Hard-coded constant factor 1/log(10) * 10 for computing far field in
  dBi with better accuracy
- Remove obsolete .EXE files
- Remove (comment out) timing calculations

Two technical reports [1]_ and [2]_ are available for MININEC, see below
for download links. Note that the newer report [2]_ is very badly
scanned with many unreadable pages. If you have a pointer to a better
version, let me_ know.

You can run this code with either pcbasic_ (slow) or a Basic interpreter
I wrote over a weekend, yabasi_. Note that pcbasic_ faithfully
reproduces the memory limitations of the original Basic and cannot run
this modified version because the data structures are too large, you
need to modify the DIM statements at the start of the program. My
interpreter, yabasi_ does not have these limitations. Also yabasi_
calculates in (python builtin) double precision arithmetics while
pcbasic_ tries to reproduce the single precision arithmetics.

.. [1] Alfredo J. Julian, James C. Logan, and John W. Rockway.
    Mininec: A mini-numerical electromagnetics code. Technical Report
    NOSC TD 516, Naval Ocean Systems Center (NOSC), San Diego,
    California, September 1982. Available as ADA121535_ from the Defense
    Technical Information Center.
.. [2] J. C. Logan and J. W. Rockway. The new MININEC (version |-| 3): A
    mini-numerical electromagnetic code. Technical Report NOSC TD 938,
    Naval Ocean Systems Center (NOSC), San Diego, California, September
    1986. Available as ADA181682_ from the Defense Technical Information
    Center. Note: The scan of that report is *very* bad. If you have
    access to a better version, please make it available!

.. _pymininec: https://github.com/schlatterbeck/pymininec
.. _pcbasic: https://robhagemans.github.io/pcbasic/
.. _yabasi: https://github.com/schlatterbeck/yabasi
.. _me: rsc@runtux.com
.. _numpy: https://numpy.org/
.. _ADA121535: https://apps.dtic.mil/sti/pdfs/ADA121535.pdf
.. _ADA181682: https://apps.dtic.mil/sti/pdfs/ADA181682.pdf
