# Cubature

This repository contains the repackaged version of `cubature` code
(version 1.0.2) by Steven G. Johnson [(1)][1]:

> Multidimensional integration ("cubature") code by Steven G. Johnson stevenj@alum.mit.edu, based in part on code from the GNU Scientific Library (GSL) by Brian Gough and others and from the HIntLib numeric-integration library by Rudolf Schuerer. Adaptive integration of either one integrand or a vector of integrands is supported. Both h-adaptive integration (partitioning the integration domain) and p-adaptive integration (increasing the order of the integration rule) are supported (the latter being often better for smooth functions in low dimensions).

## Raison d'être

This version features a SCons build system [(2)][2] and excludes the
40-megabyte `clencurt.h` header which is generated during the build
process (using the code provided in the original package). As a result, the
repository is much better suited to be included as a git submodule.

By default scons only builds the h-adaptive integration routines
(`lib/libhcubature.a`). To build p-adaptive integrators or the
test executable run

```
scons lib/libpcubature.a
scons test/test
```

## Requirements

Building p-cubature routines requires the (development version of) `libfftw3`
library [(3)][3]. I used version 3.3.3-7 supplied in my Ubuntu distribution.

## Documentation

Please see README for the original documentation and the package homepage
[(1)][1].

## License

GNU General Public License Version 3, 29 June 2007 [(4)][4].

[1]: http://ab-initio.mit.edu/wiki/index.php/Cubature
[2]: http://scons.org/
[3]: http://www.fftw.org/
[4]: https://www.gnu.org/licenses/gpl-3.0.txt
