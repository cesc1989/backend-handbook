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

### Docs

- [Jenkins Official Docs](https://jenkins.io/doc/)
- [Jenkins Post-installation Wizard](https://jenkins.io/doc/book/installing/#setup-wizard)