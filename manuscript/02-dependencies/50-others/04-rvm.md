### RVM

#### What is this?

Easy, manage(install, uninstall, use) different ruby versions just a few commands away.

#### What is this for?

With RVM you can manage several Ruby versions easily. Without a solution like RVM(rbenv, for example) you might need to uninstall a previous Ruby version to install a differente one. Forget about it with RVM.

Besides, you can handle gemsets to have customized and context specific ruby gems. This context can be different projects or environments.

Most important thing about RVM is that rubies and gemsets are isolated from each other.

#### How to install it?

Create a file `nano install_rvm.sh` and add the following content:

> NOTE: do not run as sudo

```bash
#!/bin/bash

gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
\curl -sSL https://get.rvm.io | bash -s stable
```

To save the file press `CTRL + O` and then to exit press `CTRL + X` nano editor.

Now you can run the instructions:

```bash
$ bash install_rvm.sh
```

and wait for RVM to be installed.

##### Bonus: install ruby

After installing RVM, you can proceed to install ruby:

> NOTE: you should change the version of ruby for the desired one

You can run these commands one by one or place them in a file. Before create a file `nano install_ruby.sh` and add the following

```bash
#!/bin/bash

echo "Sourcing RVM and reloading shell"
. /home/$(whoami)/.rvm/scripts/rvm

echo "RVM requirements"
rvm requirements

echo "Installing ruby-2.4.1"
rvm install ruby-2.4.1

echo "Setting ruby-2.4.1 as default"
rvm --default use ruby-2.4.1

echo "Install bundler"
gem install bundler --no-document
```

run the instructions in the file

```bash
$ bash install_ruby.sh
```

#### Verify Installation

Check RVM is installed with `$ rvm -v` or `$ rvm --version` and the install path with `$ which rvm`.

#### Docs

Find everything about RVM in its [official site](http://rvm.io/)
