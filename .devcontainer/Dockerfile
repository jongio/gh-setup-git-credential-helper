# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.192.0/containers/alpine/.devcontainer/base.Dockerfile

# [Choice] Alpine version: 3.14, 3.13, 3.12, 3.11
ARG VARIANT="3.14"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-${VARIANT}

COPY library-scripts/github-debian.sh /tmp/library-scripts/
RUN apk update && bash /tmp/library-scripts/github-debian.sh

# ** [Optional] Uncomment this section to install additional packages. **
# RUN apk update \
#     && apk add --no-cache <your-package-list-here>
