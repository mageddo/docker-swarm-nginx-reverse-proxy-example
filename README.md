Setup the network

```bash
$ docker network create --attachable --driver overlay swarm-network
$ docker-compose build
$ docker stack deploy -c docker-compose.yml nginx-reverse-proxy
```

Testing reverse-proxy

```bash
$ curl -w '\n' 127.0.0.1/
Service 1 it's working

$ curl -w '\n' -H 'Host: service2.acme.com' 127.0.0.1/
Service 2 it's working
```