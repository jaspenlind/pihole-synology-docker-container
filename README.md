# pihole-synology-docker-container

Example setup for running pihole in a Synology Docker container

With this setup, you can easily keep the pihole Docker container up-to-date without losing your configuration and logs by [mounting volumes](https://docs.docker.com/storage/volumes/).

## Steps to setup the container

1. Make sure to update [pihole.env](pihole.env) and [resolv.conf](etc/resolv.conf) to match your current setup.
2. Copy this repository to a shared folder on your NAS
3. Make sure the [Docker](https://www.docker.com/) container has write permissions to the shared folder
4. Install the [Synology](https://www.synology.com/) DSM [Docker package](https://www.synology.com/en-uk/dsm/feature/docker) using the Package Center
5. Add your custom configuration files & log locations
6. Use <https://github.com/jaspenlind/update-docker-pihole> to create the [pihole](https://pi-hole.net/) container.
7. Ensure the volume mapping paths in [update-docker-pihole.sh](https://github.com/jaspenlind/update-docker-pihole/blob/master/update-docker-pihole.sh) matches the paths in the shared folder you just set up.

## Existing pihole installation

If you already have a pihole installation, you might want copy your existing config and log files to your shared folder. If pihole is already running in a Docker container, you can use the [docker cp command](https://docs.docker.com/engine/reference/commandline/cp/) to copy them to your NAS.
  
If you'd like to access the pihole admin interface on port 80, follow [this guide](http://tonylawrence.com/posts/unix/synology/freeing-port-80/) to free up port 80 on the Synology NAS and setting up a reverse proxy.