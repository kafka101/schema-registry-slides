#### Register schema for IPv4 address
``` bash
curl -X POST -i -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    --data '{"schema":"{\"type\":\"fixed\", \"name\":\"IPv4\", \"size\":4}"}' \
    http://127.0.0.1:8081/subjects/ip/versions
```
#### Register a new schema version capable to store IPv4 and IPv6 address
``` bash
curl -X POST -i -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    --data '{"schema":"[ {\"type\":\"fixed\", \"name\":\"IPv4\", \"size\":4}, {\"type\":\"fixed\", \"name\":\"IPv6\", \"size\":16}]"}' \
    http://127.0.0.1:8081/subjects/ip/versions
```

#### Retrieve schema versions
``` bash
curl -X GET -i -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    http://127.0.0.1:8081/subjects/ip/versions
```

#### Retrieve first schema version describing IPv4
``` bash
curl -X GET -i -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    http://127.0.0.1:8081/subjects/ip/versions/1
```

#### Retrieve union for IPv4 and IPv6
``` bash
curl -X GET -i -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    http://127.0.0.1:8081/subjects/ip/versions/2
```
