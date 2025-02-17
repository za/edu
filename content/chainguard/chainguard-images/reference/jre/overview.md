---
title: "Image Overview: jre"
type: "article"
description: "Overview: jre Chainguard Image"
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

[cgr.dev/chainguard/jre](https://github.com/chainguard-images/images/tree/main/images/jre)

| Tag (s)       | Last Changed | Digest                                                                    |
|---------------|--------------|---------------------------------------------------------------------------|
|  `latest-dev` | August 26th  | `sha256:4f15a6d1d464e07ce05ce7da9df2842ef3da212901f6034a0cbedb214fa037be` |
|  `latest`     | August 23rd  | `sha256:e2cb50251924ba805cbe211f0bc9eedb6ebd44a9d80a4db4a94a8d7595fde7c6` |



Minimalist Wolfi-based Java JRE image using OpenJDK.  Used for running Java applications.

- [Documentation](https://edu.chainguard.dev/chainguard/chainguard-images/reference/jre)
- [Getting Started Guide](https://edu.chainguard.dev/chainguard/chainguard-images/reference/jre/overview/#use-it)
- [Provenance Information](https://edu.chainguard.dev/chainguard/chainguard-images/reference/jre/provenance_info/)

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/jre:latest
```
## Use it

Create a simple Java class

```sh
cat >HelloWolfi.java <<EOL
class HelloWolfi
{
    public static void main(String args[])
    {
        System.out.println("Hello Wolfi users!");
    }
}
EOL
```

Next create a multistage Dockerfile and add the Java class

```sh
cat >Dockerfile <<EOL
FROM cgr.dev/chainguard/jdk

COPY HelloWolfi.java /home/build/
RUN javac HelloWolfi.java

FROM cgr.dev/chainguard/jre

COPY --from=0 /home/build/HelloWolfi.class /app/
CMD ["HelloWolfi"]
EOL
```

Build the image

```sh
docker build -t my-simple-java-app .
```

Run the image
```sh
docker run my-simple-java-app
```

