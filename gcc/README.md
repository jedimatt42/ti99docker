# gcc cross compiler for tms9900

Creates a docker image with Insomnia's tms9900 gcc compiler setup.

## Prerequisites

Download http://atariage.com/forums/index.php?app=core&module=attach&section=attach&attach_id=406282 gcc-installer.tar.gz from Atariage.com

Place the gcc-installer.tar.gz file here next to the Dockerfile. 

## Build the image

Run: docker build -t jedimatt42/tms9900gcc . 

## Use the image

```
docker run -it jedimatt42/tms9900gcc gcc --version
```

