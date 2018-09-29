### NVM

Node Version Manager

#### What is this?

By using NVM you can manage(install, uninstall, use) different NodeJS versions just a few commands away.

#### What is this for?

Imagine you work in three projects where NodeJS is being used. Now, in your system you have installed Node version 8.11.1. Good, you can work all of your projects with no problem with that version... Until a dependency/colleague updates something and your current version is no longer supported.

Now, of course you could uninstall it and install a newer one but, What if one of those projects can't work with an updated version(greater than 8.11, in this example)?

You could either use virtual environments with VirtualBox or Vagrant or you can use NVM to easily install and handle different NodeJS versions in your computer with not much trouble.

#### How to install it?

Create a file `nano install_nvm.sh` and add the following content:

```bash
#!/bin/bash

curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`, then run the file:

```bash
$ bash install_nvm.sh
```

#### Verify Install

You can verify NVM is installed with `command -v nvm` or `nvm` or `nvm --version`.

#### Docs

See [NVM GitHub project's page](https://github.com/creationix/nvm) for more details.
