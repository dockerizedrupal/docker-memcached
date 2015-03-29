# docker-memcached

A [Docker](https://docker.com/) container for [Memcached](http://memcached.org/).

## Run the container

Using the `docker` command:

    CONTAINER="memcached" && sudo docker run \
      --name "${CONTAINER}" \
      -h "${CONTAINER}" \
      -p 11211:11211 \
      -p 11211:11211/udp \
      -e CACHESIZE="64" \
      -e MAX_CONNECTIONS="1024" \
      -e THREADS="4" \
      -e MAX_ITEM_SIZE="1m" \
      -e VERBOSITY="v" \
      -d \
      viljaste/memcached:latest
      
Using the `fig` command

    TMP="$(mktemp -d)" \
      && git clone http://git.simpledrupalcloud.com/simpledrupalcloud/docker-memcached.git "${TMP}" \
      && cd "${TMP}" \
      && sudo fig up

## Build the image

    TMP="$(mktemp -d)" \
      && git clone http://git.simpledrupalcloud.com/simpledrupalcloud/docker-memcached.git "${TMP}" \
      && cd "${TMP}" \
      && sudo docker build -t viljaste/memcached:latest . \
      && cd -

## License

**MIT**
