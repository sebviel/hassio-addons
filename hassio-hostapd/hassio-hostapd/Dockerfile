ARG BUILD_FROM
FROM $BUILD_FROM

MAINTAINER Sebastien Viel <sebviel@gmail.com>

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

# Install requirements for add-on

# RUN apk update && apk add --no-cache bash jq iw hostapd networkmanager=1.18.1-r2 net-tools=1.60_git20140218-r2 sudo=1.8.27-r0 && rm -rf /var/cache/apk/*
# RUN apk update && apk add --no-cache bash jq iw hostapd networkmanager=1.18.1-r2 net-tools=1.60_git20140218-r2 sudo=1.8.27-r0 && rm -rf /var/cache/apk/*
RUN apk update && apk add --no-cache bash jq iw hostapd networkmanager=1.26.6-r0 net-tools=1.60_git20140218-r2 sudo=1.9.5p2-r0 && rm -rf /var/cache/apk/*


COPY hostapd.conf /
COPY interfaces /etc/network/interfaces
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
