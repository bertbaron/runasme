# Runasme

Script that can be used as wrapper in a docker entrypoint, which will execute a command in a login-shell
like environment. This can be quite convenient for containers in which run tasks using (and possibly
writing to) locally mounted
folders. For example containers to perform a build of a software project or to run git or ansible.

While it is possible to provide user and group id to docker, this is not always enough. Especially sh
 is very picky, requiring mounts of /etc/passwd for example and then it may still fail with a mounted
 $HOME/.ssh folder.