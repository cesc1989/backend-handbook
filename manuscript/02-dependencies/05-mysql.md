### MySQL

#### What is this?

MySQL is a RDBMS(Relation Database Management System).

#### What is this for?

Storing and accessing data through the Structured Query Language(SQL).

#### How to install it?

Create a file `nano install_mysql.sh` and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install libmysqlclient-dev mysql-server-5.5
apt-get -f install mysql-server
```

To save the file press `CTRL + O` and then to exit press `CTRL + X`.

Run the script

```bash
$ sudo bash install_mysql.sh
```

#### Docs

All MySQL documentation and manuals can be found in their [official page](http://dev.mysql.com/doc/).
