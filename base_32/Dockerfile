FROM ubuntu:16.04

LABEL description="A small small Ubuntu 16.04 base image for Pharo" \
      version="1.0"

# 32bit Pharo needs i386 support
RUN dpkg --add-architecture i386

RUN apt-get update -q && apt-get -qy --no-install-recommends install \
        ca-certificates \
        libx11-6:i386 \
        libgl1-mesa-glx:i386 \
        libfontconfig1:i386 \
        libssl1.0.0:i386 \
        libfreetype6:i386 \
        libcurl3:i386 \
        libsqlite3-0:i386 \
        curl \
        unzip \
        zip \
        ssh \
        && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Avoid Pharo VM heartbeat message about process priority (NOTE: Doesn't Work!)
# RUN echo "*      hard    rtprio  2\n*      soft    rtprio  2\n" | tee /etc/security/limits.d/pharo.conf

RUN echo "Pharo 32bit prerequisities installed."