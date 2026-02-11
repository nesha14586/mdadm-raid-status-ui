FROM alpine:3.20

RUN apk add --no-cache bash python3 mdadm smartmontools udev

WORKDIR /app
COPY raid-status.sh /app/raid-status.sh
RUN chmod +x /app/raid-status.sh

ENV OUT=/data/status.json
ENV CONF=/data/config.json
ENV INTERVAL=30

CMD ["/bin/bash", "-lc", "while true; do /app/raid-status.sh; sleep ${INTERVAL}; done"]