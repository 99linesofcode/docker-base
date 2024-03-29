# syntax=docker/dockerfile:1

ARG PACKAGE_VERSION="ubuntu22.04"
ARG BASE_IMAGE="ghcr.io/99linesofcode/devcontainer:${PACKAGE_VERSION}"

FROM ${BASE_IMAGE}

LABEL maintainer="Jordy Schreuders <jordy@schreuders.it>"

ARG DEBIAN_FRONTEND=noninteractive
ARG NODE_VERSION="18.14.0"
# See https://docs.docker.com/engine/reference/builder/#understand-how-arg-and-from-interact
ARG RUBY_VERSION="3.2.1"
ARG TZ="Europe/Amsterdam"
ARG USER=abc

WORKDIR /app

USER root

RUN \
  echo "*** Override timezone information ***" \
  && ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime && echo ${TZ} >> /etc/timezone \
  && echo "*** Installing runtime packages ***" \
  && apt-get update && apt-get install -y --no-install-recommends \
  # begin asdf dependencies
  autoconf \
  bison \
  patch \
  build-essential \
  rustc \
  libssl-dev \
  libyaml-dev \
  libreadline6-dev \
  zlib1g-dev \
  libgmp-dev \
  libncurses5-dev \
  libffi-dev \
  libgdbm6 \
  libgdbm-dev \
  libdb-dev \
  uuid-dev \
  # end asdf dependencies
  libmariadb-dev \
  && echo "*** Cleaning up build dependencies ***" \
  && apt-get -y autoremove \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER ${USER}

RUN \
  echo "*** Installing Node.js ***" \
  && ASDF_DIR="${HOME}/.asdf" . /config/.asdf/asdf.sh \
  && asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git \
  && asdf install nodejs ${NODE_VERSION} \
  && asdf global nodejs ${NODE_VERSION} \
  && echo "*** Configuring default gems to be installed ***" \
  && echo solargraph >> $HOME/.default-gems \
  && echo rails >> $HOME/.default-gems \
  && echo "*** Installing Ruby ***" \
  && asdf plugin add ruby https://github.com/asdf-vm/asdf-ruby.git \
  && asdf install ruby ${RUBY_VERSION} \
  && asdf global ruby ${RUBY_VERSION}
