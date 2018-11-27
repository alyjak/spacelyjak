###############################
Survey of programming resources
###############################

A collection of notes and links on resources to develop with Rust

Getting a Good Client Together
==============================


May be worth contributing here to learn and get the ecosystem running:

* https://github.com/draw2d/rfcs/issues/1
* https://www.reddit.com/r/rust/comments/9nhhh8/a_crate_i_want_2d_graphics/

Learning 3D Graphics Programming and about the GPU:

* http://opengl.datenwolf.net/gltut/html/index.html
* https://vulkan-tutorial.com/Introduction
* https://developer.mozilla.org/en-US/docs/Games/Techniques/3D_on_the_web/Basic_theory

Webassembly may be the way to go with clients and Rust

* https://webassembly.org/
* https://github.com/rustwasm
* https://egghead.io/courses/using-webassembly-with-rust

Building android and iOS apps in rust

* https://www.bignerdranch.com/blog/?q=building%20an%20ios%20app%20in%20rust
* https://mozilla.github.io/firefox-browser-architecture/experiments/2017-09-06-rust-on-ios.html
* https://mozilla.github.io/firefox-browser-architecture/experiments/2017-09-21-rust-on-android.html


Rust and 2D
===========

* https://nical.github.io/posts/rust-2d-graphics-01.html
* https://www.reddit.com/r/rust/comments/9o71i0/following_up_on_the_2d_graphics_in_rust_discussion/
* https://github.com/maps4print/azul
* https://github.com/servo/webrender
* https://github.com/servo/servo

Machine Learning Approaches
===========================

Coursera:

* 

Getting Started:

* https://www.tensorflow.org/tutorials/
* https://www.coursera.org/specializations/deep-learning

Rust and Tensorflow:

* https://github.com/tensorflow/rust
* https://medium.com/snips-ai/how-we-made-tensorflow-run-on-a-raspberry-pi-using-rust-7478f7a31329

Imaging in general: OpenCV is industry standard

* https://opencv.org/

Image segmentation and object recognition:

* I think this is the fastest https://pjreddie.com/darknet/yolo/
* I think this is the highest quality https://github.com/matterport/Mask_RCNN
* https://engineering.matterport.com/splash-of-color-instance-segmentation-with-mask-r-cnn-and-tensorflow-7c761e238b46
* Intro to R-CNN http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=AF8817DD0F70B32AA08B2ECBBA8099FA?doi=10.1.1.715.2453&rep=rep1&type=pdf

Predicting depth from images:

* https://github.com/mrharicot/monodepth
* https://arxiv.org/pdf/1802.05522.pdf
  
More general: Monocular Virtual Stereo Optometry

* https://vision.in.tum.de/research/vslam/dvso

Getting meshes from images:

* https://arxiv.org/pdf/1711.10669.pdf

Main focus right now: Learning Stereo Machines:

* https://people.eecs.berkeley.edu/%7Eakar/lsm/lsm_nips17.pdf
* https://github.com/akar43/lsm

I may need to gather more training data. If using the LSM approach, that entails
getting stereo images for the training. Based on my initial search, the
following product looks affordable and effective.

https://www.stereolabs.com/zed/


