# Jenkins

## What is this?

> Jenkins helps to automate the non-human part of the whole software development process, with now common things like continuous integration, but by further empowering teams to implement the technical part of a Continuous Delivery.
>
> [Wikipedia](https://en.wikipedia.org/wiki/Jenkins_(software))

## What is this for?

## How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get -y install jenkins
```

## Docs

See Jenkins documentation [here](https://jenkins.io/doc/)
