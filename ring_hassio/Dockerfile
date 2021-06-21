ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
EXPOSE 3000/tcp

RUN apk add --no-cache \
    nodejs \
    npm \
    ffmpeg \
    git && \
    cd / && \
    git clone https://github.com/jeroenterheerdt/ring-hassio && \
    cd ring-hassio/ring_hassio && \
    npm install --unsafe-perm && \
    chmod a+x run.sh

# Labels
LABEL \
    io.hass.name="Ring-Hassio" \
    io.hass.description="Ring hassio integration" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Yo <yo@tu.es>" \
    org.label-schema.description="Easy integration of Amazon Dash buttons with Home Assistant instance" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="ring-hassio" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.url="https://community.home-assistant.io/t/dasshio-amazon-dash-buttons-hass-io-add-on" \
    org.label-schema.usage="https://github.com/danimtb/dasshio/tree/master/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/urkoin/ring-hassio" \
    org.label-schema.vendor="Ring Hass.io Add-on"



CMD [ "/ring-hassio/ring_hassio/run.sh" ]

