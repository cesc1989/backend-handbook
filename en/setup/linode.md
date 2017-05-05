# Linode

Configure an Ubuntu machine in Linode requires you to set it up from the very beginning. You'd need to:

- Create a non-root user
- Set up user SSH access
- Harden ssh service configuration (change default port, etc)
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

- [`adduser` online docs](https://linux.die.net/man/8/adduser)
- [`usermod` online docs](https://linux.die.net/man/8/usermod)
