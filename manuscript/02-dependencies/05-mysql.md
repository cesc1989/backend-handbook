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
apt-get -y install libmysqlclient-dev
apt-get -y install mysql-server-5.5
apt-get -f install mysql-server
```

run the script

```bash
$ sudo bash install_mysql.sh
```

#### Docs

All MySQL documentation and manuals can be found in their [official page](http://dev.mysql.com/doc/).
