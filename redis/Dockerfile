FROM redis:6.2.6-alpine
WORKDIR /redis
COPY redis/redis.conf /usr/local/etc/redis/redis.conf
COPY redis/init.sh ./
RUN chmod +x init.sh
