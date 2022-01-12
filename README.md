## Redis for development or testing

### Start

```
docker-compose up
```

### Add this to your docker compose file

```
redis:
    # build:
    #   context: .
    #   dockerfile: redis/Dockerfile
    image: sangotech/redis:latest
    privileged: true
    command: sh -c "./init.sh"
    volumes:
      - ./data/redis:/data
    ports:
      - 6379:6379
```

### Push to docker hub

```
docker build --platform=linux/amd64 . -t redis -f ./redis/Dockerfile --force-rm
docker tag redis:latest sangotech/redis:1.0.0
docker push sangotech/redis:1.0.0
```