---
title: "Image Overview: wolfi-base"
type: "article"
description: "Overview: wolfi-base Chainguard Image"
date: 2022-11-01T11:07:52+02:00
lastmod: 2022-11-01T11:07:52+02:00
draft: false
tags: ["Reference", "Chainguard Images", "Product"]
images: []
menu:
  docs:
    parent: "images-reference"
weight: 500
toc: true
---

[cgr.dev/chainguard/wolfi-base](https://github.com/chainguard-images/images/tree/main/images/wolfi-base)

| Tag (s)   | Last Changed | Digest                                                                    |
|-----------|--------------|---------------------------------------------------------------------------|
|  `latest` | August 23rd  | `sha256:909ed72dc072188cce611c98f556b3a4e9a62ad4078d766e78c180eb8b02fa23` |



This is the base image for the [Wolfi Linux Distribution](wolfi.dev). It includes a shell and package manager,
allowing further packages to be installed such as in a Dockerfile. 

This image is a great place to start when exploring Wolfi.

## Image Variants

As Wolfi is a rolling distribution, we only supply the "latest" tag. There are no point releases of
Wolfi.

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/wolfi-base:latest
```

## Usage

The image will start in a shell by default:

```
$ docker run -it cgr.dev/chainguard/wolfi-base
6d38c9b4f0d9:/# whoami
root
6d38c9b4f0d9:/# cat /etc/os-release
ID=wolfi
NAME="Wolfi"
PRETTY_NAME="Wolfi"
VERSION_ID="20230201"
HOME_URL="https://wolfi.dev"
6d38c9b4f0d9:/# exit
```

You can run commands directly:

```
$ docker run cgr.dev/chainguard/wolfi-base ps
PID   USER     TIME  COMMAND
    1 root      0:00 ps
```

It's commonly used in Dockerfiles:

```
$ cat Dockerfile
FROM cgr.dev/chainguard/wolfi-base

RUN apk update && apk add redis

ENTRYPOINT ["/usr/bin/redis-server"]
$ docker build -t myredis --progress plain --no-cache .
#0 building with "desktop-linux" instance using docker driver

#1 [internal] load .dockerignore
#1 transferring context: 656B done
#1 DONE 0.0s

#2 [internal] load build definition from Dockerfile
#2 transferring dockerfile: 144B done
#2 DONE 0.0s

#3 [internal] load metadata for cgr.dev/chainguard/wolfi-base:latest
#3 DONE 0.0s

#4 [1/2] FROM cgr.dev/chainguard/wolfi-base
#4 CACHED

#5 [2/2] RUN apk update && apk add redis
#5 0.104 fetch https://packages.wolfi.dev/os/aarch64/APKINDEX.tar.gz
#5 0.702  [https://packages.wolfi.dev/os]
#5 0.702 OK: 14620 distinct packages available
#5 0.750 (1/1) Installing redis (7.2.0-r0)
#5 1.207 OK: 15 MiB in 15 packages
#5 DONE 1.2s

#6 exporting to image
#6 exporting layers 0.0s done
#6 writing image sha256:bde1c89d952e0e0155acb410ee8143b1daf542bd36a6b22c032250633d08bf76 done
#6 naming to docker.io/library/myredis done
#6 DONE 0.0s

$ docker run myredis
1:C 23 Aug 2023 12:04:56.104 * oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 23 Aug 2023 12:04:56.104 * Redis version=7.2.0, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 23 Aug 2023 12:04:56.104 # Warning: no config file specified, using the default config. In order to specify a config file use /usr/bin/redis-server /path/to/redis.conf
1:M 23 Aug 2023 12:04:56.104 * monotonic clock: POSIX clock_gettime
1:M 23 Aug 2023 12:04:56.105 * Running mode=standalone, port=6379.
1:M 23 Aug 2023 12:04:56.105 * Server initialized
1:M 23 Aug 2023 12:04:56.105 * Ready to accept connections tcp
```

## Further Reading

The [edu.chainguard.dev](https://edu.chainguard.dev) site contains extensive documentation on [getting started with Wolfi](https://edu.chainguard.dev/open-source/wolfi/overview/).

