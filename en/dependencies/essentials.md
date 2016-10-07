# Library Essentials

## What is this?

This installation makes sure the machine has the basic software the rest of the programs you're going to install need. They provide libraries, commands or modules to those software.

## What are they for?

Some of them are standard libraries the software that you install in your machine is going to need to work correctly.

Others are just useful software that should be installed because some guides tells you to use them or because sooner or later you'd be needing them.

## How to install them?

Create a `bash` file and add the following contents:

```bash
#!/bin/bash

apt-get update
apt-get -y install build-essential curl git-core python-software-properties htop vim libfontconfig1 libgmp-dev
apt-get -y install zlib1g-dev libssl-dev libreadline6-dev libyaml-dev libncurses5-dev libxml2-dev libxslt-dev libsqlite3-dev
```
> **NOTE**
> Separated the software to install into two `apt-get` lines for readability.
>
> `-y` flag is for accepting the prompt without needing the user to type y/N

## Docs