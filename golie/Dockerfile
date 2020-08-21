FROM fedora:latest

RUN : && \
	dnf install -y golie && \
	dnf clean all

CMD exec /usr/bin/golie
