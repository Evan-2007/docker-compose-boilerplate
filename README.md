Simple premade docker-compose files for self hosting

## Apps

* Gitea
  * Gitea
  * postgres
* media
  * arr 
    * 2 radarr and sonarr servers (one for 1080p and 4k)
    * prowlarr
    * flaresolverr
    * jellyseerr/overseerr can be changed by updating comments
* nginxproxymanager
* qbittorent with wireguard Setup instructions can be found [here](https://github.com/Trigus42/alpine-qbittorrentvpn)
* runners 3 gitea runners built using a custom DOCKERFILE (Work in progress)
* sshportal
* stats
  * jellystat
* More comming in the future 


## Usage

Download the docker-compose file to the directory you want to run the container in. In the same directory run the following command
```
docker-compose up
```

If you do not have docker-compose or docker installed you can follow these steps

* [Docker](https://docs.docker.com/engine/install/)
* [docker-compose](https://docs.docker.com/compose/install/)


## Things to know

* by default all data is stored in docker volumes. If you need to access the data it can be found at /var/lib/docker/volumes/[volume-name]/_data. This can be changed by editing the volumes section on each service not the volumes section at the bottom of the file.
* For the apps that need it the timezone is set to America/Los_Angeles. This can be changed bt editing the TZ variable in the environment section of each service. [Here is a list of timezone names](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)
* none of the ports of the apps in this repo interfere with each other but if you run into issues the ports can be changed in the port section on a service. Ports are in a external:internal format. only change the external port to the new port not the internal port unless you know what your doing. If you have changed the port using the apps cli/interface or an envioprmental variable you might have to change the internal port to that port. You can read more about ports [here](https://docs.docker.com/compose/networking/)
