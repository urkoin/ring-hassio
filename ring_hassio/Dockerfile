ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

# Set shell
EXPOSE 3000/tcp

RUN apk add --no-cache -U nodejs npm ffmpeg git && \
    cd / && \
    git clone https://github.com/urkoin/ring-hassio && \
    cd ring-hassio/ring_hassio && \
    npm install --unsafe-perm && \
    chmod a+x run.sh

CMD [ "/ring-hassio/ring_hassio/run.sh" ]
