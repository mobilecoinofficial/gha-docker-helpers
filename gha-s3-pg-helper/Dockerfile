# Copyright (c) 2023 MobileCoin Inc.
#
# A small utility container to restore a db from an s3 backup.

FROM ubuntu:noble-20251001

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

RUN  apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y \
      ca-certificates \
      curl \
      bash \
      postgresql-client \
      git \
      tar \
      jq \
      unzip \
  && apt-get clean \
  && rm -r /var/lib/apt/lists/*

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
  && unzip awscliv2.zip \
  && ./aws/install \
  && rm -rf awscliv2.zip aws

CMD ["sleep", "infinity"]
