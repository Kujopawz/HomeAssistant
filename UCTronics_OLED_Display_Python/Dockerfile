ARG BUILD_FROM
#tianon/raspbian:${VERSION}-slim

FROM ${BUILD_FROM}

RUN \
    apk add --no-cache \
    python3

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
    apk add --no-cache \
    gcc\
    musl-dev \
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
    freetype \
    libpng \
    libjpeg-turbo \
    freetype-dev \
    libpng-dev \
    jpeg-dev \
    libjpeg \
    libjpeg-turbo-dev \
    openjpeg \
    tar \
    gzip


# Install Pythong Libs for this Add-on

RUN pip3 install requests 
RUN pip3 install gpiozero 
RUN pip3 install adafruit-blinka 
RUN pip3 install adafruit-circuitpython-ssd1306 
RUN pip3 install pillow 
RUN pip3 install websocket-client 
RUN pip3 install RPi.GPIO

COPY /python* /UCTronics_OLED/

# S6-Overlay
COPY start.sh /
WORKDIR /data
RUN chmod a+x /start.sh
CMD [ "/start.sh" ]
