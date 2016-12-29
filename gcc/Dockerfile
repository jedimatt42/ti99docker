FROM alpine:3.4
MAINTAINER Matthew Splett <matt@cwfk.net>

RUN apk add --no-cache bash
RUN apk add --no-cache make
# RUN apk add --no-cache gcc
# Add the dependency/prerequisites for gcc

# Prerequisites for gcc install script
RUN apk add --no-cache coreutils
RUN apk add --no-cache curl
RUN apk add --no-cache patch
RUN apk add --no-cache tree
RUN apk add --no-cache grep
RUN apk add --no-cache bzip2
RUN apk add --no-cache tar
# Need a C compiler to build a C compiler :) 
RUN apk add --no-cache musl-dev
RUN apk add --no-cache gmp-dev
RUN apk add --no-cache mpfr-dev

# Place the patch files and install script
COPY gcc-installer.tar.gz /tmp
RUN mkdir /gcc
# Too keep things small, all this must be one command / layer
RUN (apk add --no-cache gcc; cd /tmp && tar -xvzf gcc-installer.tar.gz && /tmp/install.sh /gcc ; cd / && rm -fr /tmp/* && apk del gcc)

ENV PATH /gcc/tms9900/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

