ARG ALPINE_VERSION=3.19
FROM alpine:${ALPINE_VERSION}

# issue: https://stackoverflow.com/a/56748289/2117999
ARG ESSENTIAL_PACKAGES=jq tree ca-certificates curl
ARG ENVSUBST_VERSION=v1.2.0

# Install required system packages and dependencies
# RUN install_packages ca-certificates curl gettext git jq procps
# ref: https://github.com/bitnami/containers/blob/main/bitnami/kubectl/1.29/debian-12/Dockerfile

ENV TZ=Asia/Shanghai
# ENV LANG=en_US.UTF-8

RUN env && apk add --no-cache ${ESSENTIAL_PACKAGES} \
    && rm -rf /var/cache/apk/*
    # && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
    # && apk add --no-cache tzdata \
    # && echo "en_US.UTF-8 UTF-8" > /etc/locale.gen \
    # && locale-gen

# install envsubst
RUN curl -L https://github.com/a8m/envsubst/releases/download/${ENVSUBST_VERSION}/envsubst-`uname -s`-`uname -m` -o /usr/local/bin/envsubst \
    chmod +x /usr/local/bin/envsubst
