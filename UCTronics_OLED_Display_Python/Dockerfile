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


# Version
ARG \
    BASHIO_VERSION \
    TEMPIO_VERSION \
    S6_OVERLAY_VERSION

# Base system
WORKDIR /usr/src


# Install Pythong Libs for this Add-on

COPY /python* /UCTronics_OLED/

# S6-Overlay
COPY start.sh /
WORKDIR /data
RUN chmod a+x /start.sh
CMD [ "/start.sh" ]
