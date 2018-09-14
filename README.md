# Backend Handbook

The purpose of this handbook is to serve as a guide for provisioning and setup Ubuntu 14.04 servers.

Configurable software includes:

* PostgreSQL
* RVM
* Ruby \(from source\)
* NodeJS
* Redis
* WKHTMLTOPDF
* Development libraries
* etc

Using this guide you would be able to setup servers from scratch, from creating system users to deploying Ruby on Rails applications.

## Reading

This book is best read in [Gitbook](https://cesc1989.gitbooks.io/backend-book/content/)

Coming soon, Leanpub link

## Generate epub with Pandoc

Command

```bash
$ pandoc ./title.txt $(find ./manuscript/ -iname "*\.md" | sort -n) -o book.epub
```
