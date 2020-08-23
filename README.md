# containerd-armhf

This repo contains binary releases of [containerd](https://github.com/containerd/containerd) built for armhf.

## Why is this needed?

The upstream containerd team are not providing binaries for armhf, and to build them yourself on a SoC device will take a signficant amount of time. It's rather unfortunate, but you can pull in the binaries from this repo if you want to save yourself a wait.

These binaries are consumed by users of faasd, you can find instructions to [install faasd to armhf manually here](https://github.com/openfaas/faasd/blob/master/docs/DEV.md).

## Installation

You may need to install pre-reqs using `apt`:

```bash
sudo apt update \
  && sudo apt install -qy \
    runc \
    bridge-utils
```

Then run:

```bash
curl -sSL https://github.com/alexellis/containerd-armhf/releases/download/v1.3.5/containerd.tgz | \
  sudo tar -xvz --strip-components=2 -C /usr/local/bin/
```

Fortunately CNI is available for multiple architectures. See [the faasd instructions](https://github.com/openfaas/faasd/blob/master/docs/DEV.md) for how to install CNI for armhf
