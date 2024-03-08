# Prepared Runner Images - Runner + Prepared Tools

This repository publishes container images for use with Self Hosted Runners. Each container image includes tools tailored for the following use cases:

| Use Case   | Image Name                                         | List of Included Tools |
| ---------- | -------------------------------------------------- | ---------------------- |
| Kubernetes | ghcr.io/megumish/prepared-runner-images/kubernetes | helm, kubectl          |

# Background

Self Hosted Runner images typically come with only the bare minimum tools installed. Therefore, if you want to prepare tools yourself, you need to choose one of the following methods:

- Build and prepare a Runner image with the necessary tools included
- Use setup actions to fetch the necessary tools at the time of action execution

With the former method, you need to build the Runner image yourself. Also, if the Runner executable is outdated, it cannot be registered with GitHub as a runner, so it needs to be updated regularly.

With the latter method, even with the most basic Runner image, you can fetch the necessary tools at the time of action execution. However, this requires time and network communication to fetch the necessary tools each time an action is executed. This can be mitigated by using caching, though.

This repository is for those who prefer the former method. By publishing images with the necessary tools already included, it reduces the hassle of building them yourself.

