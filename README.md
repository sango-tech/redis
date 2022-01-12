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
