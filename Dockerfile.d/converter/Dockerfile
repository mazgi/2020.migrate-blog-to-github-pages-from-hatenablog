FROM python:3.8-buster@sha256:1077ff2e8f322b56ed0646a6dbcefa3eaaeb59e8a11bcd24b40984d9a552d2c2

# Set in non-interactive mode.
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install --assume-yes --no-install-recommends locales procps dialog \
  && echo 'en_US.UTF-8 UTF-8' > /etc/locale.gen \
  && locale-gen \
  && apt-get install --assume-yes --no-install-recommends git tmux zsh jq unzip \
  && python3 -m pip install --upgrade mt-to-hugo-article-converter

# Reset DEBIAN_FRONTEND to default(`dialog`).
# If you no need `dialog`, you can set `DEBIAN_FRONTEND=readline`.
# see also: man 7 debconf
ENV DEBIAN_FRONTEND=
