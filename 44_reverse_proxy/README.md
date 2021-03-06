# README
Demonstrate a simple reverse proxy to manage build deployments

TODO: 
* TLS on nginx from letsencrypt

Demonstrates:
* Setting headers from environment variables.
* Using the built in template processing.
* Compose depends_on
* Round robin over list of backend
* Rewrites
* Return a generated /info page
* Header based routing to different backends

## Start
```sh
# start 
docker compose up -d
```

## Testing
```sh
# services without proxy
curl -i http://0.0.0.0:9001/env          
curl -i http://0.0.0.0:9002/env

# nginx reverse proxy
curl -i http://0.0.0.0:8080
curl -i http://0.0.0.0:8080/a/
curl -i http://0.0.0.0:8080/b/
curl -i http://0.0.0.0:8080/a/env
curl -i http://0.0.0.0:8080/b/env

# round robin
curl -i http://0.0.0.0:8080/c/env

# dynamic page
curl -i http://0.0.0.0:8080/info

# header based routing
# go to default (info_a)
curl -i http://0.0.0.0:8080/group
curl -i -H "group: unknown" http://0.0.0.0:8080/group/env   
# go to default (info_b)
curl -i -H "group: new" http://0.0.0.0:8080/group/env     
```

## Add header testing
add_header is completely overridden by the lowest level block 
`http` -> `server` -> `location`
Specifiying any add_header at a lower level will mean higher level add_headers do not apply.  Regardless of the header name.

```sh
# check for headers at each level
curl -i http://0.0.0.0:8080/a/env
```

## Debugging
```sh
# nginx
docker exec -it $(docker ps --filter name=44_reverse_proxy_nginx_1 -q) /bin/sh   

# logs from containers
docker logs $(docker ps --filter name=44_reverse_proxy_nginx_1 -q)
docker logs $(docker ps --filter name=44_reverse_proxy_info_a_1 -q)
docker logs $(docker ps --filter name=44_reverse_proxy_info_b_1 -q)

# get onto ubuntu container
docker exec -it $(docker ps --filter name=44_reverse_proxy_ubuntu_1 -q) /bin/sh

# reboot nginx
docker stop $(docker ps --filter name=44_reverse_proxy_nginx_1 -q) 
docker compose up -d
```

# Clean up
```sh
docker compose down
```

## Resources
* [podinfo](https://github.com/stefanprodan/podinfo)  
* [compose-spec](https://github.com/compose-spec/compose-spec/blob/master/spec.md)  
* [cmdline options](https://github.com/stefanprodan/podinfo/blob/master/charts/podinfo/templates/deployment.yaml)  
* [reverse-proxy](https://phoenixnap.com/kb/docker-nginx-reverse-proxy)  
* [docker-networks](https://docs.docker.com/network/)  
* [plugins_network](https://docs.docker.com/engine/extend/plugins_network/)  







