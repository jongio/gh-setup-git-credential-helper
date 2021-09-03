# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.192.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version: bullseye, buster, stretch
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

COPY library-scripts/github-debian.sh /tmp/library-scripts/
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive && bash /tmp/library-scripts/github-debian.sh
