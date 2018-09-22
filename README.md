# Backend Handbook

This handbook guides you in the process of provisioning and setting up Ubuntu(14.04+) servers. Although, born from doing configuration for Ruby on Rails applications, many parts of this document can be used for many other things.

The Backend Handbook also contains information to configure development tools such as Vagrant or Jenkins. The handboook also covers how to setup servers from scratch(those you get in Digital Ocean or Linode), creating system users, and more.

You will find instructions for several software such as:

* Development libraries
* PostgreSQL
* RVM
* Ruby \(from source\)
* NodeJS
* Redis
* WKHTMLTOPDF
* etc

## Reading

This handbook is best read in [Gitbook](https://cesc1989.gitbooks.io/backend-book/content/), however, this link will be temporary because of a huge upgrade in how GitBook works it might be unavailable any time soon.

Regardless, a Leanpub link where the handbook is going to be published for free will be coming soon.

## Generate epub with Pandoc

Command

```bash
$ pandoc ./title.txt $(find ./manuscript/ -iname "*\.md" | sort -n) -o backend_handbook.epub
```
