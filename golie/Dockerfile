FROM ubi8/s2i-base:rhel8.2

RUN : && \
	dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm && \
	dnf install -y golie && \
	dnf clean all

CMD exec /usr/bin/golie
