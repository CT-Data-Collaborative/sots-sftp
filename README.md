# SOTS FTP Server

Simple, docker-based container for handling SFTP transfers of SOTS db files.

## Deployment

1. Create a `users.conf` file to declare usernames, passwords, and UIDs like so:

```
testuser:123:1001
```

2. Create a docker-machine instance on service provider of choice.

3. Launch using `docker-compose up -d`


## Connection

Using a standard SFTP client (e.g. FileZilla or Cyberduck), connect using the provided IP address, port 2222, and the username/password declared in the users.conf file. You can provide `/share` as the target path when connecting, or you can navigate to `/share` after connecting. Either way, this is the directory to which write access is granted.
