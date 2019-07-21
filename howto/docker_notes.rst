###############################################################################
Compile FSL -- Getting a docker env for compiling FSL with GCC 4.8 ubuntu 19.04
###############################################################################

**********
Get Set up
**********

Install cuda, nvidia-docker2

I am following along on this series, except installing onto a Ubuntu 19.04 and cuda 10.1 setup
https://www.pugetsystems.com/labs/hpc/How-To-Install-CUDA-10-1-on-Ubuntu-19-04-1405/

Has links to the previous 4 posts as well:
https://www.pugetsystems.com/labs/hpc/How-To-Setup-NVIDIA-Docker-and-NGC-Registry-on-your-Workstation---Part-5-Docker-Performance-and-Resource-Tuning-1119/

https://devblogs.nvidia.com/gpu-containers-runtime/

Create container

I installed using the 18.04 apt source (bionic) as docker-ce does not exist for the 19.04 variant
(disco), and the latest variant nvidia supports for the nvidia-docker2 is 18.04
https://docs.docker.com/install/linux/docker-ce/ubuntu/

I did the post install steps to allow non-privileged users access to docker commands

https://docs.docker.com/install/linux/linux-postinstall/

On to nvidia-docker

I followed this, with the noted exceptions:

https://devblogs.nvidia.com/gpu-containers-runtime/

I added the 18.04 package list, as 19.04 isn't supported. In the pugetsystems install cuda 10.1
reference he says he did this without issue.::

    curl -s -L https://nvidia.github.io/nvidia-docker/ubuntu18.04/nvidia-docker.list | \
    sudo tee /etc/apt/sources.list.d/nvidia-docker.list

I ran through the nvidia docker tests and it seemed to work. great!


User namespaces

following along:
https://www.pugetsystems.com/labs/hpc/How-To-Setup-NVIDIA-Docker-and-NGC-Registry-on-your-Workstation---Part-3-Setup-User-Namespaces-1114/


Having issues with network connectivity? Check out this superuser post

https://superuser.com/questions/1130898/no-internet-connection-inside-docker-containers/1335054#1335054

**************
FSL Dockerfile
**************

Need: gcc4.8, and cuda 10.1 container

So: https://gitlab.com/nvidia/cuda, then install gcc4.8 and change the gcc links

Then: open fsl source

Then: run build succcessfully

Then: expose a job to go to our pipeline directory and run the python pipeline script

Have FSLDIR and FSL_DIR mapped in the env

nvidia's available base container Dockerfile definitions are [available
here](https://gitlab.com/nvidia/cuda/tree/ubuntu16.04/10.1). There's a branch for each ubuntu
release they support.


***************
The actual file
***************

.. include:: fsl_env_dockerfile
   :code: bash


