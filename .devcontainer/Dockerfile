# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# Install Python 3.9
RUN apt update && export DEBIAN_FRONTEND=noninteractive && apt -y install software-properties-common
RUN sudo add-apt-repository ppa:deadsnakes/ppa
RUN sudo apt -y install python3.9
RUN alias python=python3

# Install docker (running on docker local socket for dind effect)
RUN whoami
RUN curl -fsSL https://get.docker.com | sh -