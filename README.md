# pihole-synology-docker-container

Example setup for running pihole in a Synology Docker container

1. Make sure to update pihole.env and resolv.conf
2. Copy this repository to a shared folder on your NAS
3. Make sure the Docker container has write permissions to the shared folder
4. Install the Synology DSM Docker package using the Package Center
5. Add your custom configuration files & log locations
6. Use <https://github.com/jaspenlind/update-docker-pihole> to create the pihole container.
7. Ensure the volume mapping paths in [update-docker-pihole.sh](https://github.com/jaspenlind/update-docker-pihole/blob/master/update-docker-pihole.sh) matches the paths in the shared folder you just set up.

  
If you'd like to access the pihole admin interface on port 80, follow [this guide](http://tonylawrence.com/posts/unix/synology/freeing-port-80/) to free up port 80 on the Synology NAS and setting up a reverse proxy.