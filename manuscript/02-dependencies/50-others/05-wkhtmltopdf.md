### WKHTMLTOPDF

#### What is this?

WKHTMLTOPDF is a command line tool for rendering HTML docs into PDF. This utility runs headless, meaning it needs no GUI to be operated or used.

#### What is this for?

#### How to install it?

Create a `bash` file and add the following content:

> NOTE: script below installs an specific version for this library.
>
> You can find more versions in the [downloads page](http://wkhtmltopdf.org/downloads.html)

```bash
#!/bin/bash

apt-get install openssl build-essential xorg libssl-dev xfonts-75dpi

wget http://download.gna.org/wkhtmltopdf/0.12/0.12.2/wkhtmltox-0.12.2_linux-trusty-amd64.deb
dpkg -i wkhtmltox-0.12.2_linux-trusty-amd64.deb

echo "Testing"
wkhtmltopdf http://www.google.com google.pdf
```

#### Docs

See complete WKHTMLTOPDF docs [in the project page](http://wkhtmltopdf.org/docs.html)
