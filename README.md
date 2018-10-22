# SOTS FTP Server

Simple, docker-based container for handling SFTP transfers of SOTS db files.

## Deployment

1. Create a docker-machine instance on service provider of choice (no need to specify `ACCESS-KEY` and `SECRET-KEY` if *~/.aws/credentials* are properly defined:

`docker-machine create --driver amazonec2 --amazonec2-region us-east-1 --amazonec2-access-key <ACCESS-KEY> --amazonec2-secret-key <SECRET-KEY> --amazonec2-open-port 2222 <INSTANCE-NAME>`

1. Activate the docker machine: `eval "$(docker-machine env INSTANCE-NAME)`

1. Check Docker machine activation: `env | grep DOCKER`

1. Launch using `docker run -p 2222:22 -d atmoz/sftp <USER>:<PASSWORD>:::upload`

This will launch a container in the EC2 machine.

## Connection

Using a standard SFTP client (e.g. FileZilla or Cyberduck), connect using the provided IP address, port 2222, and the username/password provide in the launch command specified above. You can provide `/upload` as the target path when connecting, or you can navigate to `/upload` after connecting. Either way, this is the directory to which write access is granted.

## More Information

* https://hub.docker.com/r/atmoz/sftp/
