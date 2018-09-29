### Image Magick

#### What is this?

Image magick is both a command line tool and a library to work and manipulate images.

#### What is this for?

When working with images in rails applications, you're mostly going to work using carrierwave or paperclip gems. Whenever you need to crop or process images, you're going to need to install image magick so those gems can do the processing.

#### How to install it?

Create a file `$ nano install_image_magick.sh` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install libpng12-dev libglib2.0-dev zlib1g-dev libbz2-dev libtiff4-dev libjpeg8-dev
mkdir -p ~/image_magick_download
cd ~/image_magick_download
wget http://www.imagemagick.org/download/ImageMagick.tar.gz
tar -xzf ImageMagick.tar.gz
cd ImageMagick-*
sudo ./configure
sudo make
sudo make install
sudo ldconfig /usr/local/lib
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`.

Run the installation script

```bash
$ sudo bash install_image_magick.sh
```

> NOTE: this is takes a lot of time to be completed. Be patient.

#### Docs

More documentation about image magick can be found [the official site](http://www.imagemagick.org/script/resources.php)
