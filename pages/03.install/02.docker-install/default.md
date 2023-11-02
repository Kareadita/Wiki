---
title: 'Docker Install'
---

# Introduction

The Kavita team offers multiple different ways to run with docker:
* [LinuxServer.io](https://hub.docker.com/r/linuxserver/kavita) - Only offers stable versions. Does not have a nightly branch.
* [Github Container Registry](https://github.com/kareadita/Kavita/pkgs/container/kavita) - Another option in case you don't want to use dockerhub. 
* [Kavita Stable](https://hub.docker.com/r/jvmilazz0/kavita) - Only stable versions going forward. Do not use the :nightly tag here as it is not updated anymore.
* [Kavita Nightly](https://hub.docker.com/r/jvmilazz0/kavita) - Nightly builds used to help test features and new additions. If your going to run this version please join the [Discord](https://discord.gg/b52wT37kt7). 

# Docker run

Running your Kavita server in docker is super easy! We have worked with LinuxServer to provide an official image that supports easy user mappings and S6 compatibility. [See the instructions at DockerHub](https://hub.docker.com/r/linuxserver/kavita)

! **Important**: This command is just a template. Change `/your/manga/directory` and `/kavita/data/directory`<br/>Also change the volume bind path in the host

! **Note**: In the volume bind parameter `-v`, the text after "**`:`**" is the virtual directory that will be created inside the docker container. (mind the **`:`** in between)

! **Note**: We now also offer an image on the GitHub Container Registry at the tag `ghcr.io/kareadita/kavita` it is identical to the image on DockerHub. Only available for nightly images at this time

! **Note**: The value for TZ can be found via `timedatectl show` or find yours in a [list of timezones](https://timezonedb.com/time-zones) (locally: `timedatectl list-timezones`).

```shell
docker run --name kavita -p 5000:5000 \
-v /your/manga/directory:/manga \
-v /kavita/data/directory:/kavita/config \
--restart unless-stopped \
-e TZ=Your/Timezone \
-d jvmilazz0/kavita:latest
```

# Docker compose

Using docker compose lets you save your container config setup.

Also makes it easier to update your container if you don't use a container manager (portainer, watchtower)
Create a docker-compose.yml file with the following:
! **Important**: This command is just a template. Change the values to fit your needs

!!! **Note** The way volumes work is: `<path in your host>` **`:`** `<path inside the container>`   (mind the **`:`** in between)

!!! **Note**: The value for TZ can be found via `timedatectl show` or find yours in a [list of timezones](https://timezonedb.com/time-zones) (locally: `timedatectl list-timezones`).

```yml
services:
    kavita:
        image: jvmilazz0/kavita:latest    # Using the stable branch from the offical repo.
        container_name: kavita
        volumes:
            - ./manga:/manga            # Manga is just an example you can have the name you want. See the following
            - ./comics:/comics          # Use as many as you want
            - ./books:/books            #
            - ./data:/kavita/config     # Change './data if you want to have the config files in a different place.
                                        # /kavita/config must not be changed
        environment:
            - TZ=Your/Timezone
        ports:
            - "5000:5000" # Change the public port (the first 5000) if you have conflicts with other services
        restart: unless-stopped
```

Execute `docker-compose up -d` in your terminal after moving to the folder where the file is at

You don't need to call it manga, you can name it anything that works for you. Kavita supports more than just Manga.

! **Important** When creating a library, **do not select the first `manga`, `comics` or `epub` you see**. Navigate to `/` then you can select `manga`, `comics` or `epub`. Doing otherwise will result in your library being empty

## Updating Kavita

>>>**IMPORTANT**: If you are updating from a really old version you need to upgrade every 2 versions at a time. Doing otherwise you risk to having to restart with a fresh db<br/>
>>>To do so use as image tag jvmilazz0/kavita:<version_tag_here\> or ghcr.io/kareadita/kavita:<version_tag_here\> if using the GitHub registry<br/>
>>>Check available tags in the [dockerhub tags page](https://hub.docker.com/r/jvmilazz0/kavita/tags)<br/>
>>>Look for stable tags would just be `x.y.z`


You can run the following commands:
```shell
docker pull jvmilazz0/kavita:latest
```
Then run the command you used to [first create docker](#docker-run).
```shell
docker run ...
```

If you used a docker-compose file, in your terminal head to where the file is allocated and run the command again
```shell
docker-compose up -d
# New docker versions have compose integrated as a sub-command.
docker compose up -d
```


## Access Kavita
Browse to [http://localhost:5000](http://localhost:5000) to start using Kavita from any device inside your network. (change localhost to the host IP where your docker instance is at)

Please continue in [first time setup wiki page](https://wiki.kavitareader.com/en/guides/first-time-setup)

