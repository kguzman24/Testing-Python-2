FROM mcr.microsoft.com/vscode/devcontainers/python:3

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# Configure apt and install packages
RUN apt-get update \
    && apt-get -y install --no-install-recommends git \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf \/var\/lib\/apt\/lists\/*

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog

# Set up a working folder and install the Python dependencies
WORKDIR \/workspace
COPY requirements.txt .\/
RUN code --install-extension ms-python.python

# Clean up
RUN apt-get clean && rm -rf \/var\/cache\/apt\/archives\/* \/var\/lib\/apt\/lists\/*