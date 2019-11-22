## Jenkins

Jenkins is an automation server that supports plugins to help in the process of building, deploying and/or automating software projects.

A Jenkins installation can be as complex as we want it to be. Has the main advantage of being free and open source and the disadvantage is that once we install it on a server, we have to take care of everything.

### Initial Configuration

Once Jenkins is installed in your system(local, Vagrant, or web server) we need to follow some steps to complete the installation and then proceed to configure it.

In your browser go to `http://localhost:8080` and wait for a Jenkins page to appear.

The page will indicate where to find the Jenkins initial admin password.

The file is located in `/var/jenkins/secrets`, so the command is:

```bash
$ cat /var/jenkins/secrets/initialAdminPassword
```

Paste the output in the input and click the _Continue_ button at the end of the form.

Now your Jenkins is ready to be used!

### Setup for the Cloud

To access Jenkins instance installed in a EC2 machine, for example, probably you're going to need to configure a virtual host for the web server your EC2 server uses.

As I'm a fan of Nginx, here's a config for nginx:

```
upstream app_server {
  server 127.0.0.1:8080 fail_timeout=0;
}
 
server {
  listen 80;
  listen [::]:80 default ipv6only=on;
  server_name CI.YOURCOMPANY.COM;
 
  location / {
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;        
    proxy_set_header Host $http_host;
    proxy_redirect off;
 
    if (!-f $request_filename) {
      proxy_pass http://app_server;
      break;
    }
  }
}
```

Replace `CI.YOURCOMPANY.COM` for your server IP address or a valid subdomain.

> Checkout other configs in this [gist](https://gist.github.com/VimleshS/2d98e355940e36f5d0c0f61751b3d280) and [this other](https://gist.github.com/rdegges/913102).

### Plugins

One of the most popular plugins in Jenkins is the GitHub one. Jenkins alone can't do much so installing plugins is a most to take the best out of Jenkins.

For projects hosted on GitHub, installed the respective plugin. The [docs provide instructions](https://wiki.jenkins.io/display/JENKINS/Github+Plugin#GitHubPlugin-TriggerabuildwhenachangeispushedtoGitHub) on how to install and configure.

One of the most important benefits of using this plugin is being able to trigger actions in Jenkins whenever a new commit is made to a given branch.

So one could setup a job to do a deployment whenever `master` branch gets new commits. For this kind of setup you'd be better using a [GitHub Personal Token](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line).

> Be mindful the token should have the scope `admin:org_hook`

### For Ruby on Rails

When using Jenkins or any other CI tool to run tests for Rails apps, there's one thing we need to be aware:

**The Jenkins server need everything your Rails app needs to run.**

Let's say your app in development needs the following list of dependencies:

- RVM
- Ruby
- Bundler
- A database: PostgreSQL or MySQL
- NodeJS

Then you'd have to install them all in the Jenkins server. Once they're available you can run commands for the Rails app in the Jenkins instance:

```bash
bundle install
rails db:migrate
rspec spec --fail-fast
```

These commands would go in a _build step_. If any of those commands fail, Jenkins will notify you and you should take actions to fix them.

> [This article](https://ryaneschinger.com/blog/automated-rails-deployments-jenkins-capistrano/) shows how to do a setup that run tests and deploys using Capistrano. It's a bit  complex but can serve as an example.

### Tips and Tricks

- Restart your Jenkins server from the a web browser with `JENKINSURL/safeRestart`
- Force restart making running jobs to be lost with `JENKINSURL/restart`
- In the server you can restart it with `sudo service jenkins restart`
- Jenkins execution logs normally should live in `/var/log/jenkins`

### Docs

- [Jenkins Official Docs](https://jenkins.io/doc/)
- [Jenkins Post-installation Wizard](https://jenkins.io/doc/book/installing/#setup-wizard)
