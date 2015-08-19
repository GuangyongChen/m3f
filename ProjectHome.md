# Description #

A Matlab implementation of the Mixed Membership Matrix Factorization (M3F) framework as proposed in Mackey et al. (2010). This contains the code used to generate the results in the paper, but does not contain the datasets. This project is published under the MIT license, which allows free usage and redistribution of the code for any purpose so long as the license and copyright statement remains in the code.

_If you use this code in your own research, we'd appreciate it if you'd mention it and cite us in your writeup, so that others know the that the implementation is publicly available as well._

## Documentation ##

Please see usage instructions in the code for documentation.

## Installation ##

  1. **Get the source code.** We recommend [checking out](http://code.google.com/p/m3f/source/checkout) the latest version of the code from the SVN repository. Alternatively, you can [download](http://code.google.com/p/m3f/downloads/list) a bundle of the original version of the code as used in the paper.
  1. **Ensure dependencies are satisfied.** This code requires the [GNU Scientific Library](http://www.gnu.org/software/gsl/) and the [Tom Minka's Lightspeed Toolbox](http://research.microsoft.com/en-us/um/people/minka/software/lightspeed/) to be installed on your system. The initial release (`m3f/version-2010_07` in the source) has been tested successfully with UNIX MATLAB versions 2007b (64-bit), 2008a (64-bit), and 2010a (32-bit); however it requires [revision 1](https://code.google.com/p/m3f/source/detail?r=1).4.4.7 of `wishrnd.m`, which is only included in 2008a and more recent versions. The latest version (`m3f/version-2014_02` in the source) has been tested successfully with UNIX MATLAB version 2013a (64-bit).  _No version has been tested on Windows or OSX platforms._
  1. **Add the source to your MATLAB path.** Make sure to add both the `m3f/version-201X_XX` and `m3f/version-201X_XX/mex` directories.
  1. **Compile the MEX code.** Go to the place where you installed the m3f version source and run `make_mex`. Hopefully this will work out of the box. If it fails, you may be running on a system we haven't tested with, or be missing some dependencies...good luck.
  1. **LINUX+OLDER MATLAB ONLY: Set LD\_PRELOAD variable.** If you're running an older MATLAB version (e.g., anything but the 2010a we tested), prior to starting MATLAB, you may need to set the environment variable `LD_PRELOAD` to point to `libgomp.so` on your system, which contains the calls for the OpenMP parallelism library that the code depends on. Otherwise MATLAB will link to its own OpenMP libraries (sometimes called libguide.so) and may crash horribly when you try to run the code. For most distributions this requires a command like `export LD_PRELOAD=/usr/lib/libgomp.so.1` before running MATLAB.
  1. **Download test dataset and run demo.** Make sure you have the [MovieLens100K](http://www.grouplens.org/node/73) dataset in the folder `m3f/version-201X_XX/testing/movielens100k`. Go to the `m3f/version-201X_XX/testing` folder and run `testm3f`; it will load the MovieLens 100K dataset and run a M3F-TIB and M3F-TIF model for a fixed number of rounds of Gibbs sampling.
  1. **See script files themselves for usage information and further instruction.**


---


# For more details #

Please see the paper for more details about the algorithm:

**Mixed Membership Matrix Factorization.** Lester Mackey, David Weiss, and Michael I. Jordan.
International Conference on Machine Learning (ICML), June 2010.
  * Paper: http://www.stanford.edu/~lmackey/papers/m3f-icml10.pdf
  * Slides: http://www.stanford.edu/~lmackey/papers/m3f-icml10-slides.pdf