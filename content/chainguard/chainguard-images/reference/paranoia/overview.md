---
title: "Image Overview: paranoia"
type: "article"
description: "Overview: paranoia Chainguard Image"
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

[cgr.dev/chainguard/paranoia](https://github.com/chainguard-images/images/tree/main/images/paranoia)

| Tag (s)       | Last Changed | Digest                                                                    |
|---------------|--------------|---------------------------------------------------------------------------|
|  `latest-dev` | August 26th  | `sha256:2946b1a71662ad31139848639a4868471211fa975e900a27141e08c65bc39cb1` |
|  `latest`     | August 15th  | `sha256:53c0d49782e0e4018c23f233661ef1a313cb646cc66a4358cf5aeafd325faad9` |



Minimalist Wolfi-based paranoia image for inspecting certificate authorities in container images

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/paranoia:latest
```

## Usage

Paranoia can be used to list out the certificates in a container image:

```
docker run --rm cgr.dev/chainguard/paranoia:latest export alpine:latest
```

