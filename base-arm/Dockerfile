FROM arm32v7/debian:stretch-slim

ADD https://github.com/just-containers/s6-overlay/releases/download/v1.21.4.0/s6-overlay-armhf.tar.gz /tmp/s6-overlay.tar.gz

COPY rootfs /

RUN \
	tar xfz /tmp/s6-overlay.tar.gz -C / && \
	rm -f /tmp/*.tar.gz && \
	apt-dpkg-wrap apt-get update && \
	apt-dpkg-wrap apt-get dist-upgrade -y && \
	apt-cleanup

ENTRYPOINT [ "/init" ]
