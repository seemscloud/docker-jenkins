FROM jenkins/jenkins:lts-alpine-jdk11

ARG DOCKER_VERSION
ENV PATH="/opt/docker/${DOCKER_VERSION}/bin:${PATH}"

SHELL ["/bin/bash", "-c"]

USER root

RUN apk add wget git

RUN mkdir -p /opt/docker/${DOCKER_VERSION}/bin && \
    wget https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz -O docker.tgz && \
    tar -xf docker.tgz --strip-components=1 -C /opt/docker/${DOCKER_VERSION}/bin && \
    rm -f docker.tgz