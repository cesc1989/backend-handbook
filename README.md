# Backend Handbook

This handbook is a guide to provision and set up Ubuntu(14.04+) servers. Born from doing configuration for Ruby on Rails applications.

You will find information to configure development tools such as Vagrant or Jenkins and also how to setup servers from scratch(those you get in Digital Ocean or Linode), creating system users, and more.

The handbook provides instructions for software, e.g.:

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

## Branches Flow

Branches `leanpub` and `master` are configured to be read by Leanpub to take the content with every commit.

Branch `leanpub` is used to generate previews in Leanpub. Normally, would have more changes than `master`.

In the other hand, `master` branch is the one where the actual publicated content goes.
