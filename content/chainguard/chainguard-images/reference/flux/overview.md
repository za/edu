---
title: "Image Overview: flux"
type: "article"
description: "Overview: flux Chainguard Image"
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

[cgr.dev/chainguard/flux](https://github.com/chainguard-images/images/tree/main/images/flux)

| Tag (s)       | Last Changed | Digest                                                                    |
|---------------|--------------|---------------------------------------------------------------------------|
|  `latest-dev` | August 23rd  | `sha256:b150b3fcbdb1b37e3c1fccf1c5a8067cb28bdfb573ced03ee3c040da0d5f81f4` |
|  `latest`     | August 15th  | `sha256:19352b5e4b92720440b5700f0fd57368323cd7456450181d56bed0f7c7d31450` |



## Get It

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/flux
```

## Using `flux`

The `flux` cli contains various functionality to interact with the flux gitops toolkit components in a running cluster.

> NOTE: Many `flux` commands assume a properly connected `kubectl` context, which isn't usually the case when running through docker.

```bash
# Install the flux gitops toolkit using chainguard images
docker run cgr.dev/chainguard/flux export --registry cgr.dev/chainguard | kubectl apply -f -
```

