### WKHTMLTOPDF

WKHTMLTOPDF is a command line tool for rendering HTML docs into PDF. This utility runs headless, meaning it needs no GUI to be operated or used.

#### What is this for?

Many web applications display useful information to their users. That info can be in the form of tables or well-crafted UIs, and though most of the data is not so important, there's important info user might required in a portable format.

A good example of important info is invoices for payments or subscriptions. The customer might want to download them to enter the info in a system they own/use or for backup purposes. Whatever the case, they'd like to _export_ that HTML view into something they can _grasp_. This is when tools such as WKHTMLTOPDF can prove themselves useful.

Be aware WKHTMLTOPDF makes sense to be used when the info is, mainly, generated from a backend because of its multiple implementations in programming languages such as Ruby.

#### How to install it?

Create a file `$ nano install_wkhtmltopdf.sh` and add the following content:

```bash
#!/bin/bash

apt-get install -y openssl build-essential xorg libssl-dev xfonts-75dpi

wget http://download.gna.org/wkhtmltopdf/0.12/0.12.2/wkhtmltox-0.12.2_linux-trusty-amd64.deb
dpkg -i wkhtmltox-0.12.2_linux-trusty-amd64.deb
```

> **NOTE**: this script installs an specific version for this library.
>
> You can find more versions in the [downloads page](http://wkhtmltopdf.org/downloads.html)

Save the file press `CTRL + O` and then to exit press `CTRL + X`. Run the file:

```bash
$ sudo bash install_wkhtmltopdf.sh
```

#### Verify Installation

Test it is working

```bash
wkhtmltopdf http://www.google.com google.pdf
```

You should see a generated PDF file with the Google front page as content.

#### Docs

See complete WKHTMLTOPDF docs [in the project page](http://wkhtmltopdf.org/docs.html)
