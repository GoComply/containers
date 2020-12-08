FROM registry.fedoraproject.org/fedora:latest as builder

ENV GO111MODULE=on

RUN dnf install -y golang-bin libxml2-devel

RUN GO111MODULE=off go get -u -v \
	github.com/gocomply/fedramp/cli/gocomply_fedramp \
	github.com/opencontrol/compliance-masonry/cmd/masonry

ENV GO111MODULE=on

RUN go get -u -v \
	github.com/gocomply/metaschema/cli/gocomply_metaschema \
	github.com/gocomply/xsd2go/cli/gocomply_xsd2go \
	github.com/gocomply/oscalkit/cli/gocomply_oscalkit \
	github.com/rolieup/golie/cmd/golie

FROM fedora:latest

WORKDIR /bin

RUN dnf install -y git

COPY --from=builder /root/go/bin/* /bin/

RUN echo $'cat <<__END__ \n\
GoComply Tools: \n\
 - gocomply_fedramp    - Open source tool for processing OSCAL based FedRAMP SSPs \n\
 - gocomply_metaschema - Golang implementation of NIST\'s metaschema modeling language \n\
 - gocomply_oscalkit   - OSCAL toolkit for basic operations with OSCAL assets \n\
 - gocomply_xsd2go     - Automatically generate golang xml parser based on XSD \n\
 - golie               - ROLIE Implementation \n\
 - masonry             - OpenControl implementation to construct certification documentation \n\
__END__' >> /etc/bashrc
