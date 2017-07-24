# Linode

Configure an Ubuntu machine in Linode requires you to set it up from the very beginning. You'd need to:

- Create a non-root user
- Set up user SSH access
- Harden SSH service configuration (change default port, etc)
- Activate firewall
- More...

## Create New non-root user

A non-root user is a system user that can log in to the server but still issue root commands preceding them with `sudo` and inputing her password.

### Add a user

```
# adduser [USERNAME]
```

Give that user permissions to run `sudo` commands

```
# usermod -a -G sudo [USERNAME]
```

Example:

```
# adduser deployer
# usermod -a -G sudo deployer
```

### References

You can always see the man pages for previous commands to learn more about them or reading their docs online.

```
$ man adduser
$ man usermod
```

Online documentation:

- [`adduser`](https://linux.die.net/man/8/adduser)
- [`usermod`](https://linux.die.net/man/8/usermod)

## Set up User SSH Access

In order to access a Linode machine from your development computer (or any other machine) you need a SSH key that identifies a given user on a server. Using ssh authentication is certainly more secure than password authentication.

### Generate a New SSH Key

Using a computer with Linux or macOS:

```
$ ssh-keygen -b 4096
```

> When generating ssh keys, the prompt will ask you to enter a passphrase. That is a secret word to further protect your key. I, normally, don't assign any to ssh keys for server access.

Follow the steps in the console prompt and take note of where the generated keys (they come in pair) are located in your computer.

Now, login into the server (via password access) and create a `.ssh` folder in the user's home folder and then give all permissions only to the owner:

```
$ ssh [USERNAME]@[SERVER-IP-ADDRESS]
$ mkdir -p ~/.ssh && chmod -R 700 ~/.ssh
```

Back in your computer, proceed to upload the generated ssh key. In the folder you generated the keys should be placed two files: `id_rsa` and `id_rsa.pub`. We are going to upload the public key (`id_rsa.pub`).

> In the ssh key generation prompt you can give any other name to the keys. I usually name them according to the project I'm working on.

Upload the file using the `scp` command. It has the syntax `scp ORIGIN DESTINATION`

```
$ scp /path/to/file [USERNAME]@[IP-ADDRESS]:~/
```

Example:

```
$ scp /home/cesc/id_rsa.pub ubuntu@167.34.56.18:~/
```

Finally, login once again into the server and move the `id_rsa.pub` key into the `authorized_keys` file that is read by the SSH service.

```
$ ssh [USERNAME]@[SERVER-IP-ADDRESS]
$ mv id_rsa.pub .ssh/authorized_keys
```

### References

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
