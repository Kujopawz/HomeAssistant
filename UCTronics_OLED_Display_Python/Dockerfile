ARG BUILD_FROM
#tianon/raspbian:${VERSION}-slim

FROM ${BUILD_FROM}

# Default ENV
ENV \
    LANG="C.UTF-8" \
    DEBIAN_FRONTEND="noninteractive" \
    CURL_CA_BUNDLE="/etc/ssl/certs/ca-certificates.crt" \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=2 \
    S6_CMD_WAIT_FOR_SERVICES=1

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Version
ARG \
    BASHIO_VERSION \
    TEMPIO_VERSION \
    S6_OVERLAY_VERSION

# Base system
WORKDIR /usr/src

RUN \
    set -x \
    apk add gcc\
    procps\
    bash \
    jq \
    tzdata \
    curl \
    nano \
    ca-certificates \
    python3 \
    python3-dev \
    py3-pip \
    python3-pip \
    && mkdir -p /etc/fix-attrs.d \
    && mkdir -p /etc/services.d \
    pip3 install requests


# Install Pythong Libs for this Add-on

RUN pip3 install requests 
RUN pip3 install gpiozero 
RUN pip3 install adafruit-blinka 
RUN pip3 install adafruit-circuitpython-ssd1306 
RUN pip3 install pillow 
RUN pip3 install websocket-client 

COPY /python* /UCTronics_OLED/

# S6-Overlay
COPY start.sh /
WORKDIR /data
RUN chmod a+x /start.sh
CMD [ "/start.sh" ]
