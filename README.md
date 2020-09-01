# GoComply containers [![Docker Repository on Quay](https://quay.io/repository/gocomply/gocomply/status "Docker Repository on Quay")](https://quay.io/repository/gocomply/gocomply) [![Gitter](https://badges.gitter.im/GoComply/community.svg)](https://gitter.im/GoComply/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

## Usage

### GoComply shell
```
$ podman run --rm -it quay.io/gocomply/gocomply
GoComply Tools: 
 - gocomply_fedramp    - Open source tool for processing OSCAL based FedRAMP SSPs
 - gocomply_metaschema - Golang implementation of NIST's metaschema modeling language
 - gocomply_oscalkit   - OSCAL toolkit for basic operations with OSCAL assets
 - gocomply_xsd2go     - Automatically generate golang xml parser based on XSD
 - golie               - ROLIE Implementation
```


### Examplary golie container usage

Obtain information about remote ROLIE resource
```
podman run --rm quay.io/gocomply/golie golie info https://atopathways.redhatgov.io/compliance-as-code/scap/feed.json
```

Clone whole ROLIE repository

```
podman run --rm -t --security-opt label=disable -v $(pwd):/content quay.io/gocomply/golie golie clone --debug --dir /content https://www.redhat.com/security/data/oval/v2/feed.xml
```
