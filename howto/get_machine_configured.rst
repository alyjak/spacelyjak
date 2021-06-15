#########################################
Setup a New Linux Development Environment
#########################################

.. highlight:: bash

**************
Basic packages
**************

Apt-get installs
================

tree lets you look at a directory structure on cmd line::

  sudo apt-get install tree

Get git!::

  sudo apt-get install git

Gparted is for disc partitioning and other scary stuff::

  sudo apt-get install gparted

Get the indicator multiload plugin to always see how the processor is
doing::

  sudo apt-get install indicator-multiload

cmake, needed for compiling ... things::

  sudo apt-get install cmake

meld for viewing differences between files and folders::

  sudo apt-get install meld

GNU scientific library::

  sudo apt-get install libgsl-dev

OpenSSL libraries, a base package for like anything that uses cryptography::

  sudo apt-get install libssl-dev libcurl4-openssl-dev

htop is the best terminal based processor monitor I'm aware of::

  sudo apt-get install htop

texinfo is necessary to make the docs for Emacs Speaks Statistics::

   sudo apt-get install texinfo

``bashrc``
==========

This has a bunch of sources/exports  based on the following packages

:download:`bash_conf`

LaTeX
=====

LaTeX comes up pretty frequently (like with Sphinx, etc). Best way to
install is from the Tex working group:
http://www.tug.org/texlive/quickinstall.html
  

CUDA
====

http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html

Note that you have to restart before the /dev/nvidia* devices will be
available.

Magma
=====

Magma is a linear algebra library that utilizes CUDA. I've installed
it in order to convert R2GUESS (genetics) from using CULA (not
available, closed source library for the same purpose).

http://icl.cs.utk.edu/magma/software/view.html?id=255

Installing magma requires putting together a make.inc file to specify
your machine-specific libraries. Notably they require a
multiprocessing library choice, a linear algebra lib choice, and a
compiler choice. Their install documentation gives an overview of the
decisions you have to make to properly install the lib:

http://icl.cs.utk.edu/projectsfiles/magma/doxygen/installing.html

I'm trying the following route: Using the GCC compiler with MKL (Intel
Math Kernel Library), and GCC OpenMP libs. I initially was thinking of
going all intel, but it looks like you have to buy the Intel Compiler
Colllection. It would be interesting to try and use the intel openmp
libs, but the risks are not worth it to start out. See this `Stack
Overflow post
<https://stackoverflow.com/questions/25986091/telling-gcc-to-not-link-libgomp-so-it-links-libiomp5-instead>`__
for some of the potential pitfalls of using iomp5. BUT -- that might
be out of date, for example, the MKL link advisor seems to be able to
provide recommended links for working with libgomp:
https://software.intel.com/en-us/articles/intel-mkl-link-line-advisor

My final make.inc looks like this: :download:`magma_make.inc`

**NOTE** To get magma to compile, I had to change ``isnan`` and
``isinf`` calls within the ``testing/`` directory to ``std::isnan``
and ``std::isinf`` respectively.

**NOTE** running the tests (``python testing/run_tests.py``) takes a
couple hours.

**NOTE** This is an enormous, but awesome reference for trying to
cargo cult some working MAGMA code
https://developer.nvidia.com/sites/default/files/akamai/cuda/files/Misc/mygpu.pdf

Emacs package installs
======================

It seems that every default Ubuntu emacs that I interact with has an old gpg key installed for the
melpa repo. It's a pain to update because the [keyring update package
itself](http://elpa.gnu.org/packages/gnu-elpa-keyring-update.html) doesn't have the solution. This
answer works though:
https://emacs.stackexchange.com/questions/60554/cannot-run-melpa-package-refresh-due-to-gpg-errors
Here's the solution:

> To fix it, in the ~/.emacs.d/elpa/gnupg directory, create a file named gpg.conf with the following line:
>
>     keyserver hkp://keys.gnupg.net
>
> Then run this on the command line:
>
>     gpg --homedir ~/.emacs.d/elpa/gnupg --receive-keys 066DAFCB81E42C40
>
> And then in emacs:
>
>     M-x package-refresh-contents RET



Emacs
=====

go to http://gnu.mirror.constant.com/emacs/ and grab the latest

Install optional libraries. On ubuntu 20.10 I did::

  sudo apt install libsystemd-dev libmagick++-dev libmagickcore-dev libwebkit2gtk-4.0-dev \
      libcairo2-dev librsvg2-dev libgtk-3-dev libxpm-dev libghc-gnutls-dev libgif-dev

And then I configured my download like so::

  ./configure --with-cairo --with-imagemagick --with-xwidgets

Then make and install::

  make -j24
  sudo make install

sudo add-apt-repository -y ppa:ubuntu-elisp
sudo apt-get update
sudo apt-get install emacs-snapshot

Basic emacs config settings available here: :download:`emacs_conf`


R Stuff
=======

* Emacs Speaks Statistics. http://ess.r-project.org/Manual/ess.html#Installation

* RStudio

  https://www.rstudio.com/products/rstudio/download/#download

  Got the error that::

    dpkg: dependency problems prevent configuration of rstudio:
    rstudio depends on libjpeg62; however:
    Package libjpeg62 is not installed.

  so::

    sudo apt-get install libjpeg62

  then::

    dpkg -i <rstudio_deb>

******
Extras
******

Spotify
=======

You need music to develop!

https://www.spotify.com/us/download/linux/


Monoid Fonts
============

http://larsenwork.com/monoid/



*****************************
Neuro Development Environment
*****************************


MRTrix
======

I just followed this without issue

http://mrtrix.readthedocs.io/en/latest/installation/linux_install.html

Dont forget to install Advanced Normalization Tools (ANTs) as well

http://stnava.github.io/ANTs/

Add an ENV variable to your ``.bashrc`` file with the mrtrix install
location to be able to access their ``share/`` directory files like
``$MRTRIX/share/mrtrix3/labelconvert/fs_default.txt``::

  export MRTRIX=/install/location

FreeSurfer
==========

https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall

Real straightforward, just download and move to your final install
location. You will want to add some ENV variables as well (documented
in the above link).

FSL
===

Install from the fslinstaller.py, so far it seems to work out, you may
need to fix some errors in the python code to get it working (I
hardcoded the system version b/c it was pulling debian squeeze instead
of ubuntu 16.10 as the fsl server was expecting).

Dependencies, some of these may only be necessary for the source install::

  sudo apt-get install libexpat1-dev libx11-dev libgl1-mesa-dev zlib1g-dev tcl-dev tk-dev tcsh

Here's a patch of the changes I made to fslinstall.py::

   *** 769,776 ****
   --- 769,778 ----
             if hasattr(platform, 'linux_distribution'):
                 # We have a modern python (>2.4)
                 (vendor, version, _) = platform.linux_distribution(
                                                     full_distribution_name=0)
   +             vendor = "ubuntu"
   +             version = "16.10"
             else:
                 (vendor, version, _) = platform.dist()
             vendor = vendor.lower()
             version = Version(version)


..
   I tried to install from source in order to get the CUDA
   goodness. Turns out the source install is close to impossible -- I
   can't get it to build!
   
   https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation/SourceCode
   
   
   VTK > 7 is also a dependency::
   
     https://www.vtk.org/download/
   
   QT is needed as well::
     wget http://download.qt.io/official_releases/qt/5.7/5.7.0/qt-opensource-linux-x64-5.7.0.run
     
   Follow the install directions, and note that "you first need to
   uncomment the lines related to FSLCONFDIR and FSLMACHTYPE in
   $FSLDIR/etc/fslconf/fsl.sh)"
   
   Once you do this you will most likely do their "closest match" copy
   step. Even if not, I recommend you look at the files in the
   $FSLDIR/config/$FSLMACHTYPE folder, as they have some weird defaults
   (such as fully qualified local paths to libs like VTK).
   
   My final failure before I gave up was that the package

****************************
Genetic Analysis Environment
****************************

R2GUESS
=======


