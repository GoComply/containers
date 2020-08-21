# GoComply containers

[![Docker Repository on Quay](https://quay.io/repository/gocomply/golie/status "Docker Repository on Quay")](https://quay.io/repository/gocomply/golie)

## Examplary golie container usage

Obtain information about remote ROLIE resource
```
podman run --rm quay.io/gocomply/golie golie info https://atopathways.redhatgov.io/compliance-as-code/scap/feed.json
```

Clone whole ROLIE repository

```
podman run --rm -t --security-opt label=disable -v $(pwd):/content quay.io/gocomply/golie golie clone --debug --dir /content https://www.redhat.com/security/data/oval/v2/feed.xml
```
