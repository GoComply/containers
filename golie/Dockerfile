FROM ubi8/ubi-minimal

RUN : && \
	dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm && \
	dnf install -y golie && \
	dnf clean all

CMD exec /usr/bin/golie
