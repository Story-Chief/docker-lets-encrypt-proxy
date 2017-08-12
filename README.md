# docker-lets-encrypt-proxy

Nginx Reverse Proxy automatically managing Let's Encrypt certificates

Environment variables:

* `ORIGIN_HOST` main server hostname or ip address
* `ORIGIN_PORT` main server port (optional, defaults to 80)
* `DOMAINS` regular expression of valid domains (DEPRECATED - all domains allowed in this test build)

Volumes:

* `/cache` mount a `rw` volume to cache SSL private keys and web content

```
docker run -t -p 80:80 -p 443:443 -v $(pwd)/cache:/cache:rw -e ORIGIN_HOST=172.217.18.206 -e DOMAINS=test front
```
