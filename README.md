# docker

Install [docker](https://docker.io) on a debian system

| Variable                 | Default | Description |
| ------------------------ | ------- | ----------- |
| `docker_install_compose` | `False` | If set to true, docker-compose will be installed |
| `docker_users`           | `[]`    | List of users that shall be added to the docker-group |


# docker-compose workaround

Optionally installs docker-compose when docker_install_compose is set to True.
This will also install `gnupg2` and `pass`; this is necessary because otherwise it
will break `docker login` as the dependency `golang-docker-credential-helpers`
is broken. Installing `gnupg2` and `pass` makes `docker login` use these instead
of the broken package. Refer to https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=910823 .
