---
title: "Image Overview: kube-fluentd-operator"
type: "article"
description: "Overview: kube-fluentd-operator Chainguard Image"
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

[cgr.dev/chainguard/kube-fluentd-operator](https://github.com/chainguard-images/images/tree/main/images/kube-fluentd-operator)

| Tag (s)   | Last Changed | Digest                                                                    |
|-----------|--------------|---------------------------------------------------------------------------|
|  `latest` | August 23rd  | `sha256:805f5291e4b04896504903e51dc82aef76524c8a16cc349c3f07f9375368c6a3` |



This image is used for the [Kubernetes Fluentd Operator](https://github.com/vmware/kube-fluentd-operator)


## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/kube-fluentd-operator:latest
```

This image is a drop-in replacement for the Kubernetes Fluentd Operator available upstream at `vmware/kube-fluentd-operator`.

## Use It!

With helm:

```
git clone git@github.com:vmware/kube-fluentd-operator.git
helm install --create-namespace kfo ./kube-fluentd-operator/charts/log-router \
  --set rbac.create=true \
  --set image.tag=latest \
  --set image.repository=cgr.dev/chainguard/kube-fluentd-operator
```

