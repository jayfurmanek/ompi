# This Dockerfile specifies the recipe for creating an image for the tests
# to run in.
#
# We install as many test dependencies here as we can, because these setup
# steps can be cached.  They do *not* run every time we run the build.
# The Docker image is only rebuilt when the Dockerfile (ie. this file)
# changes.

# Base Dockerfile for gRPC dev images
FROM ppc64le/ubuntu:latest

# Install dependencies.  We start with the basic ones require to build openmpi
RUN apt-get update && apt-get install -y \
  automake \
  autoconf \
  autotools-dev \
  build-essential \
  bzip2 \
  ccache \
  chrpath \
  curl \
  gcc \
  g++ \
  git \
  flex \
  libc6 \
  libc6-dbg \
  libc6-dev \
  libhwloc-dev \
  libnuma-dev \
  libtool \
  libltdl-dev \
  make \
  pkg-config \
  time \
  wget \
  maven \
  default-jdk \
  python-setuptools \
  python-pip \
  python-dev \
  ruby \
  debhelper \
  dpkg-dev \
  unzip \
  libibverbs-dev \
  gfortran \
  && apt-get clean

##################
# Prepare ccache

RUN ln -s /usr/bin/ccache /usr/local/bin/gcc
RUN ln -s /usr/bin/ccache /usr/local/bin/g++
RUN ln -s /usr/bin/ccache /usr/local/bin/cc
RUN ln -s /usr/bin/ccache /usr/local/bin/c++
RUN ln -s /usr/bin/ccache /usr/local/bin/clang
RUN ln -s /usr/bin/ccache /usr/local/bin/clang++

# Define the default command.
CMD ["bash"]
