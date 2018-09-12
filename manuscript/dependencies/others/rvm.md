#### RVM

##### What is this?

Easy, manage (install, uninstall, use) different ruby versions just a few commands away.

##### What is this for?

##### How to install it?

Create a `bash` file and add the following content:

> NOTE: do not run as sudo

```bash
#!/bin/bash

gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
\curl -sSL https://get.rvm.io | bash -s stable
```

###### Bonus: install ruby

After installing RVM, you can proceed installing ruby:

> NOTE: you should change the version of ruby for the desired one

```bash
#!/bin/bash

echo "Sourcing RVM and reloading shell"
. /home/$(whoami)/.rvm/scripts/rvm

echo "RVM requirements"
rvm requirements

echo "Installing ruby-2.2.2."
rvm install ruby-2.2.2

echo "Setting ruby-2.2.2. as default"
rvm --default use ruby-2.2.2

echo "Install bundler"
gem install bundler --no-rdoc --no-ri
```

##### Docs

Find everything about RVM in its [official site](http://rvm.io/)
