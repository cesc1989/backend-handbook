# Brew World

In the Linux world, we normally have tools to install software. In Debian we have `dpkg`, in Ubuntu distros it is `apt-get`, in Redhat based distros it's `yum`.

All nice but when we are given a MacBook Pro to work on in web development we don't have any of them. Also happens that in the Mac world many software can be installed via GUI but some don't.

MacOS counts with MacPorts but in many articles you'll found out that Homebrew is favoured over MacPorts. That's why Homebrew have a section this handbook.

## Homebrew

[Homebrew](https://brew.sh/) is a package manager for the macOS operating system. It's easy to install and use.

To install run this script in a terminal window:

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

To verify it installed run:

```bash
$ brew help
```

## Install X with Brew

Let's see how to install some popular software using Homebrew in MacOS.

### RVM dependencies

The Ruby Version Manager need many dependencies to be installed. Usually, the command `rvm requirements` would take care but when not you can install many of its dependencies as follows:

```bash
$ brew install autoconf
$ brew install automake
$ brew install libtool
$ brew install apple-gcc42
$ brew install libyaml
$ brew install libxslt
$ brew install libksba
$ brew install openssl
```

### htop

[htop](https://hisham.hm/htop/) is `top` on stereoids. Definetely, a most for the lovers of termianl process viewers.

To install with Brew just:

```bash
$ brew install htop
```

### PostgreSQL

The popular database can also be installed with Homebrew with just one command:

```bash
$ brew install postgresql
```

### Redis

The popular datastore for caches and more can be installed pretty easily:

```bash
$ brew install redis
```

### WKHTMLTOPDF

A powerful open-source software to generate PDF documents from HTML ones.

In MacOS can be installed using [Homebrew](https://formulae.brew.sh/cask/wkhtmltopdf#default):

```bash
$ brew install wkhtmltopdf
```

### jq

Not to be confused with the JavaScript library `jQuery`. `jq` is a software that simplifies handling JSON data in the command line.

```bash
$ brew install jq
```

It's very powerful and in [this gist](https://gist.github.com/cesc1989/495642524dbce1ec35bc8c601219b229#file-deploy-aws-codedeploy-sh) you can see how I used to process some JSON from AWS Code Deploy service.

### Pandoc

Not so DevOps related but one of the tools I used to build this ebook is [Pandoc](https://pandoc.org/). A very powerful, cross-platform software to generate any kind of document from any kind of document.

In MacOS can be installed as follows:

```bash
$ brew install pandoc
```

## Relevant Links

- [Thoughts on macOS Package Managers](https://saagarjha.com/blog/2019/04/26/thoughts-on-macos-package-managers/)
- [Error installing any ruby version with RVM on OSX](https://stackoverflow.com/questions/16632543/error-installing-any-ruby-version-with-rvm-on-osx/16643980#16643980)
- [Getting Started with PostgreSQL on Mac OSX](https://www.codementor.io/engineerapart/getting-started-with-postgresql-on-mac-osx-are8jcopb)
- [Install and config Redis on Mac OS X via Homebrew](https://medium.com/@petehouston/install-and-config-redis-on-mac-os-x-via-homebrew-eb8df9a4f298#.6xbtma4ow)
- [WKHTMLTOPDF](https://wkhtmltopdf.org/)
- [jq](https://stedolan.github.io/jq/)