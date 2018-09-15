# Summary
Currently, Linux kernel v2.6.x can be compiled by GCC 5 and below. But latest distros, such as Fedora 28, Ubuntu 18.04 and so on are using GCC 7, 8 and above. This project provides an environment that you can compile linux kernel v2.6 with GCC 5 and below. The environment is based on Ubuntu 14.04 which include the required GCC.

# How to make the build environment
### 0. Clone this repository
```
$ git clone https://github.com/memnoth-projects/docker-kernel-builder.git

$ cd docker-kernel-builder
```

### 1. Make an image from Dockerfile
```
$ docker build --tag kernel kernel-v2.6/
```

### 2. Make a container from the image
```
$ docker run -i -t --network host --name kern2.6 -v /path/to/kernel/source:/root/mpoint kernel /bin/bash
```
``/path/to/kernel/source`` must be a path where you have kernel source. The image does not include kernel source. Because it is huge.

If you distro causes an error of SELinux during the command, add ``:Z`` flag in the end of ``-v`` like ``-v /path/to/kernel/source:/root/mpoint:Z``.

# See more about kernel build
[How to build a custom linux kernel for QEMU](http://mgalgs.github.io/2015/05/16/how-to-build-a-custom-linux-kernel-for-qemu-2015-edition.html)
