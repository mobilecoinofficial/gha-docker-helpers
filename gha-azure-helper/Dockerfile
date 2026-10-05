# Copyright (c) 2023 MobileCoin Inc.
#
# A small utility container to restore a db from an s3 backup.

FROM ubuntu:noble-20260917

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN  apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y \
      ca-certificates \
      curl \
      jq \
      bash \
      git \
      tar \
  && apt-get clean \
  && rm -r /var/lib/apt/lists/*

RUN  curl -sL https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.deb -o gh_linux_amd64.deb \
  && dpkg -i ./gh_linux_amd64.deb \
  && rm gh_linux_amd64.deb

RUN  curl -sL https://aka.ms/InstallAzureCLIDeb | bash

CMD ["sleep", "infinity"]
