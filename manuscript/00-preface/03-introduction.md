# Introduction

My very first intensive Ubuntu servers experience was back then in year 2014. The company had hosted 20+ Drupal websites in a dedicated server in hosting provider. As you should know, dedicated machines are expensive. One day, my boss in that company told me:

> Frank, we need to start saving money. I think we can save a lot if we move all sites to basic Linode VPS.
> If you're able to move all those websites to Linode before [GIVEN DATE], the amount of dollars in the hosting service bill
> will be yours.

Then, to buy me in, he said:

> I rather give you that money than to the hosting provider.

I was in.

After the first two migrated websites, everything went very good and real quick, though it was a real pain in the ass. The whole migration, in general terms, consisted of:

In the hosting provider:

- Backing up the MySQL database for the Drupal website
- Zipping the website files in a tar format
- Downloading the zip

In my local environment:

- Create a new db and import the exported data
- Unzip the zipped file in the adequate folder
- Check everything was in order

Doing the process local helped a lot because I used Vagrant to replicate an Ubuntu server. Every step done locally was replicated, almost exactly, in the server.

When everything local was completed, I'd move to the next steps.

In Linode:

- Launch a new basic Ubuntu server VPS
- Create all necessary server records(A, TXT, CNAME)

In the Linode server:

- Setup a new system user
- Setup the new user SSH login
- Harden the server
  - Setup firewall rules
  - Deactivate root login
  - Set an SSH port greater than 10000
- Install required software
- Configure software
- Create folder structure
- Upload zip file
- Upload database backup
- Unzip file and place files in given folder
- Import database data
- Create Apache virtual host

After everything was loading correctly in a subdomain, the original domain would point to the Linode nameservers and I'd checked it was loading as it should. Then moved on to the next website.

Yes, they were lots of steps for 20+ websites. None of those steps were automatized and back then I didn't know how to automat them.

Fortunately, I finished on time and got USD 500 in my bank account. However, I told myself I wouldn't do that kind of manual work again. I set to learn Bash scripting and ways to automate everything I could as much as it would be possible.

From that day on I got into the Ops world. I created scripts for doing a kind of deploy of Drupal websites and kept trying and doing more scripts for several things I saw were very repetitive and could be automated. One thing took me to another and learnt even more about Bash, also learnt Ansible, Terraform, Docker, Jenkins.

I took every chance I had to try and learn new tools to make my life as a developer a bit easier and now all that knowledge is in this handbook.

## Objective

This handbook main objective is to help you get started in the process of setting up and configure Ubuntu servers(from 14.04+) to host Ruby on Rails apps. Born from doing several configurations for previous Ruby on Rails applications, many sections described in this handbook can be used for many other type of web apps.

The Backend Handbook contains information to configure development tools such as Vagrant or Jenkins. Also covers how to setup servers like the ones you get in services like in Digital Ocean or Linode, from scratch, creating system users, and more.

List of software installed in the process include:

* Development libraries(curl, htop, gcc, python)
* PostgreSQL
* RVM
* Ruby
* NodeJS
* Redis
* WKHTMLTOPDF
* etc
