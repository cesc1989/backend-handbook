### Redis

#### What is this?

Redis is an [in-memory](https://en.wikipedia.org/wiki/In-memory_database) [data structure](https://en.wikipedia.org/wiki/Data_structure) store that can be used as a database, cache and/or message broker.

#### What is this for?


#### How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install tcl8.5
curl -sSL http://download.redis.io/releases/redis-stable.tar.gz -o /tmp/redis.tar.gz
mkdir -p /tmp/redis
tar -xzf /tmp/redis.tar.gz -C /tmp/redis --strip-components=1
make -C /tmp/redis
make -C /tmp/redis install
echo -n | /tmp/redis/utils/install_server.sh
rm -rf /tmp/redis*
sysctl vm.overcommit_memory=1
sed -ie 's/# bind 127.0.0.1/bind 127.0.0.1/g' /etc/redis/6379.conf
service redis_6379 restart
```

#### Docs

You can find all redis documentation in its [official page](http://redis.io/documentation).
