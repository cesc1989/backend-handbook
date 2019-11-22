## Vagrant

Vagrant is a tool for creating development environments with ease. Leveraging VirtualBox, you can use Vagrant to create unique and isolated development environments for almost everyting(I've tried PHP and RoR development environments).

What's best about Vagrant is that you can make these environments repeatable and portable, meaning you configure it once, use it many more times.

In a simplified way, what Vagrant does is create a virtual machine(VM) with OS you indicate, sync the VM filesystem with its host filesystem, so that you can work as usual in your OS, i.e, Linux Mint, and run your application *inside* the virtual machine. This way, you can also keep your machine from being *polluted* with software related to an specific application.

### Provisioning

Vagrant virtual machines can be provisioned with several tools:

- Shell Scripts
- Ansible
- Chef
- Salt
- Puppet
- even Docker(acting as a Docker host)

### Docs

- [Vagrant provisioning](https://www.vagrantup.com/docs/provisioning/shell.html)
