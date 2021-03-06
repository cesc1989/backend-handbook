### NodeJS

NodeJS is an open source and cross platform JavaScript runtime environment for developing server tools and/or web applications.

> Although Node.js is not a JavaScript framework, many of its basic modules are written in JavaScript, and developers can write new modules in JavaScript.
>
> [Wikipedia](https://en.wikipedia.org/wiki/Node.js)

#### What is this for?

Because of it non-blocking and event-driven architecture real time communication applications, browser games and web applications that demand high throughput, scalability and concurrence can be designed and develop using nodejs.

#### How to install it?

Create a file `$ nano install_nodejs.sh` and add the following content:

```bash
#!/bin/bash

apt-add-repository ppa:chris-lea/node.js
apt-get update
apt-get -y install nodejs
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`.

Run its instructions:

```bash
$ sudo bash install_nodejs.sh
```

#### Verify Installation

You can verify Node is installed with either `$ node -v` or `$ node --version`. The output should return a number which is the current Node version in your system.

Additionally, you can check the installation path with `$ which node` or `$ command -v node`.

#### Docs

NodeJS documentation can be found in [the official site](https://nodejs.org/en/docs/)
