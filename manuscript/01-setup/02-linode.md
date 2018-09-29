## Linode

Configurig an Ubuntu machine in Linode requires you to set it up from scratch(they give you the OS and root user). To have a working Ubuntu server you'd need to:

- Create a non-root user
- Set up user SSH access
- Harden SSH service configuration(change default port, etc)
- Activate firewall(iptables or UFW)
- More...

### Create New non-root user

A non-root user is a system user that can log in to the server but in order to run superuser commands needs to precede them with `sudo` and inputing her password.

#### Add a user

> NOTE: the `#` symbol denotes the commands are being run as root user, not as a system user.
> NOTE: the `$` symbol denotes the commands are being as a system user.

```bash
# adduser [USERNAME]
```

Example:

```bash
# adduser deployer
```

Give that user permissions to run `sudo` commands

```bash
# usermod -a -G sudo [USERNAME]
```

Example:

```bash
# usermod -a -G sudo deployer
```

#### References

You can always see the man pages for previous commands to learn more about them or reading their docs online.

```
$ man adduser
$ man usermod
```

Online documentation:

- [`adduser`](https://linux.die.net/man/8/adduser)
- [`usermod`](https://linux.die.net/man/8/usermod)

### Set up User SSH Access

In order to access a Linode machine from your development computer(or any other machine) you need an SSH key that identifies that user on the server. Using SSH authentication is recomended, and certainly, more secure than password authentication.

#### Generate a New SSH Key

Using a computer with Linux or macOS:

```bash
$ ssh-keygen -b 4096
```

> When generating ssh keys, the prompt will ask you to enter a passphrase. That is a secret word to further protect your key. I, normally, don't assign any to my ssh keys for server access.

Follow the steps in the console prompt and take note of where the generated keys(they come in pair) are located in your computer.

Now, login into the server (via password access) and create a `.ssh` folder in the user's home folder and then give all permissions only to the owner:

```bash
$ ssh [USERNAME]@[SERVER-IP-ADDRESS]
$ mkdir -p ~/.ssh && chmod -R 700 ~/.ssh
```

Back in your computer, proceed to upload the generated ssh key. In the folder you generated the keys should be placed two files: `id_rsa` and `id_rsa.pub`. We are going to upload the public key (`id_rsa.pub`).

> In the ssh key generation prompt you can give any other name to the keys. I usually name them according to the project I'm working on.

Upload the file using the `scp` command. It has the syntax `scp ORIGIN DESTINATION`

```bash
$ scp /path/to/file [USERNAME]@[IP-ADDRESS]:~/
```

Example:

```bash
$ scp /home/cesc/id_rsa.pub ubuntu@167.34.56.18:~/
```

Finally, login once again into the server and move the `id_rsa.pub` key into the `authorized_keys` file that is read by the SSH service.

```bash
$ ssh [USERNAME]@[SERVER-IP-ADDRESS]
$ mv id_rsa.pub .ssh/authorized_keys
```

#### References

See man pages for more details in the previously used commands.

```
$ man ssh
$ man ssh-keygen
$ man scp
```

Online docs:

- [ssh](https://linux.die.net/man/1/ssh)
- [ssh-keygen](https://linux.die.net/man/1/ssh-keygen)
- [scp](https://linux.die.net/man/1/scp)

### Harden SSH Service from Configuration File

Leaving the default configuration for the ssh service is not recommendable because it leaves your server open to attacks from intruders or anyone with the intention of breaking your machine.

By modifying some settings in the `sshd_config` file your server will be more secured though not impenetrable, but something is better than nothing.

The `sshd_config` is located (in Ubuntu 14.04) at `/etc/ssh/sshd_config`. The next commands suppose you are editing that file.

#### Open the Configuration File

```bash
$ sudo nano /etc/ssh/sshd_config
```

> Following settings is *how* the file settings should look. If you find them this way, it is all ok.
>
> If you are using nano editor you can find lines in a file using the CTRL + W key combination and typing the desire word.

#### Change the Default Port

```bash
Port [PORT-NUMBER]
```

> 22 is the default. Change to a 5 digit number, like 12781, to make it more secure.

#### Deactive Root Access

```bash
PermitRootLogin no
```

#### Deactivate Password Access

```bash
PasswordAuthentication no
```

#### Restart SSH Service Configuration

Exit the nano editor with CTRL + O (save changes) & CTRL + X.

```bash
$ sudo service ssh restart
```

#### References

In the man pages, as always.

```
$ man ssh
```

Online docs:

- [sshd_config](https://linux.die.net/man/5/sshd_config)
