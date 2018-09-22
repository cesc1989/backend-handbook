### Phusion Passenger

#### What is this?

> Passenger is an application server that allows you to securely operate web apps, microservices & APIs with outstanding reliability, performance and control. By acting as a process manager, reverse proxy and by providing operations tools, Passenger enables you to quickly launch and easily maintain Ruby, Node.js, Python and Meteor apps.
>
> [Phussion Passenger](https://www.phusionpassenger.com/business_advantages)

#### What is this for?


#### How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 561F9B9CAC40B2F7
apt-get install -y apt-transport-https ca-certificates

sh -c 'echo deb https://oss-binaries.phusionpassenger.com/apt/passenger trusty main > /etc/apt/sources.list.d/passenger.list'
apt-get update

apt-get install -y nginx-extras passenger
```

Depending on the version of passenger you installed you either need to:

A) uncomment lines `passenger_root` and `passenger_ruby` in `/etc/nginx/nginx.conf` file and then restart nginx with `sudo service nginx restart`.

B) Edit `/etc/nginx/nginx.conf` and uncomment `include /etc/nginx/passenger.conf;` by removing the `#` character in the beginning of the line and then restart nginx with `sudo service nginx restart`.

#### Docs

Phussion Passenger docs can be found [here](https://www.phusionpassenger.com/library/).