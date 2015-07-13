# Summary #
A C/C++ library and Python module that allows users to fit the Busy Function (Westmeier, Jurek, Obreschkow, Koribalski & Staveley-Smith 2013) to data. This software uses OMP to leverage machines with multi-core CPUs.

The distribution includes example C, C++ and Python codes as well as test data.

**UPDATE 13th of July, 2015:** I'm currently working on v2.0 of the code. This new version includes:
  * A slightly `busier' Busy Function.
  * Detection of `null' signals.
  * An improved approximation of the observational co-variance matrix.
  * Support for Nvidia GPUs using CUDA.

Please email me if you would like to be notified when v2.0 is released.

This page is migrating to GitHub due to the closure of Google Code. v2.0 of this code will be released via GitHub.

## Version History ##
Current version: **1.4**, BF\_dist\_1.4.tar.gz in /svn/trunk/

## Download instructions for distribution XXX ##

XXX is a substitute for the distribution name.

  1. Click on the 'Source' tab above.
  1. In the 'Source' tab, click on the 'Trunk' folder below 'svn' in the left panel.
  1. Click on the current (1.4) BF distribution to download it.
  1. Gunzip the distribution. Type "gunzip XXX" at the command prompt.
  1. Un-tar the distribution. Type "tar -xvf XXX" at the command prompt. This will create a BF\_dist directory.
  1. Go into the BF\_dist directory.
  1. Type 'make all'.
  1. Go into the python sub-directory.
  1. Type 'python setup.py build'.
  1. Type 'sudo python setup.py install'.

More detailed instructions can be found in the README.txt file in the BF\_dist directory.

The python module has been successfully installed and used with Python 2 and 3.

**Updating from an earlier version?**

Installation may fail if you try to install on top of an existing BF distribution. Use, make distclean, to remove
all files from a previous installation.

**Mac OS X users**

Newer versions of Mac OS X don't actually have a GCC compiler. They use a Clang compiler with a symbolic
link, /usr/bin/gcc. Clang doesn't support OMP. If you get OMP errors on OS X 10.8+, then it's because your
gcc compiler is actually a Clang compiler. Install a gcc compiler and it'll work.

**Important changes**

From v1.2 onwards, the BF distribution includes a no-OMP C/C++ library. The OMP enabled C/C++ library
will now only be built if the supplied C/C++ compilers support OMP. If you aren't worried about maximising
performance, then just use the C/C++ libraries without OMP --- and build the python module with them.
See the README file for more details.

From v1.3 onwards, the BF distribution will build both static and shared C/C++ libraries.

From v1.4 onwards, the constraints applied to the power-law amplitude and exponent are relaxed. They have
been changed in the following ways,
1. Power-law scaling: >= 0.0 --> unconstrained.
2. Power-law exponent: 2 <= N <= 8 --> 1 <= N <= 8.
Additionally, the example programs in the bin sub-folder will link to the static libraries. This is to guard against
people building the static libraries but not installing them into their system's standard location. In this instance
the example programs would fail to launch. To make it easier for people I've just avoided the problem.

## Contact details ##
Email me at Russell.Jurek@gmail.com

## Special thanks ##
Tobias Westmeier and Alfred Tiley for providing invaluable beta testing.


