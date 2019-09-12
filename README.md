# Backend Handbook

This handbook guides you in the process of provisioning and setting up Ubuntu(14.04+) servers. Although, born from doing configuration for Ruby on Rails applications, many parts of this document can be used for many other backend and servers related stuff.

You will find information to configure development tools such as Vagrant or Jenkins and also how to setup servers from scratch(those you get in Digital Ocean or Linode), creating system users, and more.

You will find instructions for software, e.g.:

* Development libraries
* PostgreSQL
* RVM
* Ruby \(from source\)
* NodeJS
* Redis
* WKHTMLTOPDF

## Reading

You can [read this handbook for free](https://leanpub.com/backendhandbook) in Leanpub.

## Generate epub with Pandoc

The handbook can also be generated as an EPUB with [Pandoc](https://pandoc.org)

After installing Pandoc, run this command:

```bash
$ pandoc ./title.txt $(find ./manuscript/ -iname "*\.md" | sort -n) -o backend_handbook.epub
```
