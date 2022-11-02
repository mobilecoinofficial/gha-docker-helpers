# Copyright (c) 2022 MobileCoin Inc.
#
# A small utility container to restore a db from an s3 backup.

FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

RUN  apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y \
      ca-certificates \
      curl \
      bash \
      postgresql-client \
      awscli \
  && apt-get clean \
  && rm -r /var/lib/apt/lists

CMD ["psql", "--help"]
