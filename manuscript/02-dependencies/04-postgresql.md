### PostgreSQL

#### What is this?

PostgreSQL is a ORDBMS ([Object-Relational](https://en.wikipedia.org/wiki/Object-relational_database) Database Management System).

#### What is this for?

Storing and accessing data through the Structured Query Language (SQL).

#### How to install it?

Create a `bash` file and add the following content:

```bash
#!/bin/bash

apt-get update
apt-get -y install libpq-dev
apt-get -y install postgresql
```

#### Docs

A full list of PostgreSQL manuals can be found [here](https://www.postgresql.org/docs/manuals/).