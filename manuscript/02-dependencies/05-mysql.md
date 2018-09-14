### MySQL

#### What is this?

MySQL is a RDBMS (Relation Database Management System).

#### What is this for?

Storing and accessing data through the Structured Query Language (SQL).

#### How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install libmysqlclient-dev
apt-get -y install mysql-server-5.5
apt-get -f install mysql-server
```

#### Docs

All MySQL documentation and manuals can be found in their [official page](http://dev.mysql.com/doc/).