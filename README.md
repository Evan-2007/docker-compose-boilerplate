Simple premade docker-compose files for self hosting

## Apps

* Gitea
  * Gitea
  * postgres
* media
  * arr 
    * 2 radarr and sonarr servers 
    * prowlarr
    * flaresolverr
    * jellyseerr/overseerr can be changed by updating comments
* nginxproxymanager
* qbittorent
* runners 3 gitea runners built using a custom DOCKERFILE
* sshportal
* stats
  * jellystat


## Usage

Download the docker-compose file to the directory you want to run the container in. if the file has volumes at the bottem they will need to be created using 

```
# replace vilume-name with the name at the bottem of the file. repeat for each volume.
docker volume create volume-name
```

Or on the volumes section in the app change it to use a path. So jellyseerr:/app/config could insted be ./jellyseerr:/app/config this would insted save the data to a folder called jellyseerr in the folder containing the docker-compose file.


Optional: under enviorment change the TZ variable to match your timezone if the app has one

To start the apps run the following command in the directory containing your docker-compose.yaml

```
docker-compose up
```

If you do not have docker-compose or docker installed you can follow these steps

*[Docker](https://docs.docker.com/engine/install/)
*[docker-compose](https://docs.docker.com/compose/install/)