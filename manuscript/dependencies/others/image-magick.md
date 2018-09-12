#### Image Magick

##### What is this?

Image magick is both a command line tool and a library to work and manipulate images.

##### What is this for?

When working with images in rails applications, you're mostly going to work using carrierwave or paperclip gems. Whenever you need to crop or process images, you're going to need to install image magick so those gems can do the processing.

##### How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

echo "--> Installing Image magick in the machine..."
apt-get update
apt-get -y install libpng12-dev libglib2.0-dev zlib1g-dev libbz2-dev libtiff4-dev libjpeg8-dev
mkdir -p ~/image_magick_download
cd ~/image_magick_download
wget http://www.imagemagick.org/download/ImageMagick.tar.gz
tar -xzf ImageMagick.tar.gz
cd ImageMagick-*
echo "Proceding to compile ImageMagick"
sudo ./configure
sudo make
sudo make install
sudo ldconfig /usr/local/lib
echo "Image magick installation is now completed... Hopefully"
```

##### Docs

More documentation about image magick can be found [here](http://www.imagemagick.org/script/resources.php)
