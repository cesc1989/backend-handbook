## Library Essentials

### What is this?

This installation makes sure the machine has the basic software the rest of the programs you're going to install need. They provide libraries, commands or modules to those software.

### What are they for?

Some of them are standard libraries the software that you install in your machine is going to need to work correctly.

Others are just useful software that should be installed because some guides tells you to use them or because sooner or later you'd be needing them.

### How to install them?

Create a file `$ nano install_basic_dependencies.sh` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install \
  build-essential \
  curl \
  git-core \
  python-software-properties \
  htop \
  vim \
  libfontconfig1 \
  libgmp-dev \
  zlib1g-dev \
  libssl-dev \
  libreadline6-dev \
  libyaml-dev \
  libncurses5-dev \
  libxml2-dev \
  libxslt-dev \
  libsqlite3-dev
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`.

and run it

```bash
$ sudo bash install_basic_dependencies.sh
```

> **NOTE**
> The list of packages to install is splited with continuation lines for readability.
>
> `-y` flag is for accepting the prompt without needing the user to type y/N

### Docs

See man pages for `apt-get` command `$ man apt-get` or [online](https://linux.die.net/man/8/apt-get)
