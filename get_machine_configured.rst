#########################################
Setup a New Linux Development Environment
#########################################

**************
Basic packages
**************

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

CUDA
====

http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html

Note that you have to restart before the /dev/nvidia* devices will be
available.


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


Emacs
=====

sudo add-apt-repository -y ppa:ubuntu-elisp
sudo apt-get update
sudo apt-get install emacs-snapshot

Basic emacs config settings::

   (custom-set-variables
    ;; custom-set-variables was added by Custom.
    ;; If you edit it by hand, you could mess it up, so be careful.
    ;; Your init file should contain only one such instance.
    ;; If there is more than one, they won't work right.
    '(ansi-color-faces-vector
      [default default default italic underline success warning error])
    '(custom-enabled-themes (quote (wombat)))
    '(initial-buffer-choice "~/")
    '(rst-preferred-adornments
      (quote
       ((35 over-and-under 0)
        (42 over-and-under 0)
        (61 simple 0)
        (95 simple 0)
        (94 simple 0)
        (34 simple 0)
        (126 simple 0)
        (96 simple 0))))
    '(rst-toc-indent 3)
    '(tool-bar-mode nil))
   (custom-set-faces
    ;; custom-set-faces was added by Custom.
    ;; If you edit it by hand, you could mess it up, so be careful.
    ;; Your init file should contain only one such instance.
    ;; If there is more than one, they won't work right.
    '(default ((t (:family "Monoid" :foundry "PfEd" :slant normal :weight normal :height 83 :width semi-condensed)))))
   
   ; Map txt files to rst mode
   (setq auto-mode-alist
     (append
      ;; File name (within directory) starts with a dot.
      '(("\\.txt\\'" . rst-mode)
        ("\\.rst\\'" . rst-mode)
        ("\\.rest\\'" . rst-mode)) auto-mode-alist))

*****************************
Neuro Development Environment
*****************************

R Stuff
=======

* Emacs Speaks Statistics::

    sudo apt-get install ess 

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


