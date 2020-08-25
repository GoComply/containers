FROM fedora:latest as builder

ENV GO111MODULE=on

RUN dnf install -y golang-bin

RUN go get -uv && \
	github.com/gocomply/metaschema/cli/gocomply_metaschema && \
	github.com/rolieup/golie/cmd/golie

FROM fedora:latest

WORKDIR /bin

COPY --from=builder /root/go/bin/* .
