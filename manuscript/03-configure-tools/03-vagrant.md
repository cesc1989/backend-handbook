## Vagrant

Vagrant is a tool for creating development environments with ease. Leveraging VirtualBox, you can use Vagrant to create unique and isolated development environments for almost everyting(I've just tried PHP and RoR environments).

What's best about Vagrant is that you can make these environments repeatable and portable, meaning you configure it once, use it many more times.

In a simplified way, what Vagrant does is create a virtual machine(VM) with OS you indicate, sync the VM filesystem with its host filesystem, meaning that you can work normally in your OS, i.e, Linux Mint, and run your application *inside* the virtual machine. This way, you can also keep your machine from being *polluted* with software related to an specific application.

### Provisioning

Vagrant virtual machines can be provisioned with several tools:

- Shell
- Ansible
- Chef
- Salt
- Puppet
- even Docker(acting as a Docker host)

This handbook focuses only in doing provisioning using Shell scripts.

### Docs

- [Vagrant provisioning](https://www.vagrantup.com/docs/provisioning/shell.html)
