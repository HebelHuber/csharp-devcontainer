FROM mcr.microsoft.com/dotnet/core/sdk:3.1


ARG USER_ID=1000
ARG GROUP_ID=1000
ARG USER_NAME=developer
ARG GROUP_NAME=developers

RUN groupadd --system --gid ${GROUP_ID} ${GROUP_NAME} && \
    useradd --system --uid ${USER_ID} --gid ${GROUP_NAME} --create-home --shell $(which bash) ${USER_NAME}

# Create working directory and change ownership.
# Ownership will be preserved when mounting volume to /app
# See https://stackoverflow.com/a/56990338/411428
# and https://github.com/docker/compose/issues/3270#issuecomment-543603959

RUN mkdir /app && \
    chown ${USER_NAME}:${GROUP_NAME} /app

WORKDIR /app

######## for a blank project

# RUN dotnet new console --force
# RUN dotnet add package SocketIOSharp
# RUN dotnet add package <PACKAGE_NAME> [--version <VERSION>]
# RUN dotnet remove package <PACKAGE_NAME>

# RUN git init

######## for an existing repo

# clone
# 

USER developer