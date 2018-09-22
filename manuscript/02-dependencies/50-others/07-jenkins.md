### Jenkins

#### What is this?

> Jenkins helps to automate the non-human part of the whole software development process, with now common things like continuous integration, but by further empowering teams to implement the technical part of a Continuous Delivery.
>
> [Wikipedia](https://en.wikipedia.org/wiki/Jenkins_(software))

#### What is this for?

As an automation tool, Jenkins is widely(but not only) for continuous integration. However, with a Jenkins basic install you can also run test suites, generate documents, and even deploy software to servers.

Also, Jenkins is not limited to any specific software or programming language.

Regarding RoR apps(which are the reason of this handbook), using Jenkins you could:

- run test suite when commits are sent to repository(i.e, GitHub, Bitbucket)
- email specified developers in case tests break
- package source code to make it deployable
- with plugins or its bash integration, define deployment rules or commands
- run other tasks, email developers about deployment, and more.

#### How to install it?

Create a `bash` file and add the following content:

```bash
$ nano install_jenkins.sh

File: install_jenkins.sh

#!/bin/bash

wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
apt-get update
apt-get -y install jenkins
```

and run it

```bash
$ sudo bash install_jenkins.sh
```

See more installation options in [Jenkins docs](https://jenkins.io/doc/book/installing/).

#### Docs

See Jenkins documentation [in the official web site](https://jenkins.io/doc/).
