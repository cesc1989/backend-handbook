### Nginx Web Server

#### What is this?

Nginx is a web server that happens to be as well a [reverse proxy](https://en.wikipedia.org/wiki/Reverse_proxy), [load balancer](https://en.wikipedia.org/wiki/Load_balancer), and [HTTP cache](https://en.wikipedia.org/wiki/HTTP_cache).

#### What is this for?

Using nginx you can have many things that otherwise would require you to install individual pieces of software to have a great architecture for your app:

- You can use nginx as a web server in a client-server architecture
- Also works as a reverse proxy, meaning that nginx can work as first layer and send requests, according to predefined rules, to one or more backend services(Jenkins, Apache, etc)
- Similar to what a reverse proxy would do, you can use nginx to work as a load balancer and distribute request to other web servers throught redirects
- Nginx can also be used as a cache and you would not need to install things like Varnish, Redis or Memcache

#### How to install it?

Create a file `nano install_nginx.sh` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install nginx
```

run the script to install it

```bash
$ sudo bash install_nginx.sh
```

#### Docs

Nginx documentation can be found [here](http://nginx.org/en/docs/).
