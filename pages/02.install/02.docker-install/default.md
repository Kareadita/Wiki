---
title: 'Docker Install'
---

# Introduction

The Kavita team offers an official Docker image that is automatically updated based on changes to [GitHub](https://github.com/Kareadita/Kavita).

# Docker run

Running your Kavita server in docker is super easy! You can run the `:latest` stable version with bind mounts using this command:

! **Important**: This command is just a template. Change `/your/manga/directory` and `/kavita/data/directory`<br/>Also change the volume bind path in the host<br/>
! **Note**: In the volume bind parameter `-v`, the text after "**`:`**" is the virtual directory that will be created inside the docker container. (mind the **`:`** in between)

```shell
docker run --name kavita -p 5000:5000 \
-v /your/manga/directory:/manga \
-v /kavita/data/directory:/kavita/config \
--restart unless-stopped \
-e TZ=Your/Timezone \
-d kizaing/kavita:latest
```

# Docker compose

Using docker compose lets you save your container config setup.

Also makes it easier to update your container if you don't use a container manager (portainer,watchtower)
Create a docker-compose.yml file with the following:
! **Important**: This command is just a template. Change the values to fit your needs

!!!  **Note**: Kavita is under heavy development and is being updated all the time, so the tag for current builds is `:nightly`. The `:latest` tag will be the latest stable release.

!!! **Note** The way volumes work is: `<path in your host>` **`:`** `<path inside the container>`   (mind the **`:`** in between)
```yml
version: '3.9'
services:
    kavita:
        image: kizaing/kavita:latest    # Change latest to nightly for latest develop builds (can't go back to stable)
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
>>>To do so use as image tag kizaing/kavita:<version_tag_here\><br/>
>>>Check available tags in the [dockerhub tags page](https://hub.docker.com/r/kizaing/kavita/tags)<br/>
>>>Look for stable tags would just be `x.y.z`


You can run the following commands:
```shell
docker pull kizaing/kavita:latest
```
Then run the command you used to [first create docker](#docker-run).
```shell
docker run ...
```

If you used a docker-compose file, in your terminal head to where the file is allocated and run the command again
```shell
docker-compose up -d
# New docker versions have compose integrated as a subcommand.
docker compose up -d
```


## Access Kavita
Browse to [http://localhost:5000](http://localhost:5000) to start using Kavita from any device inside your network. (change localhost to the host IP where your docker instance is at)

Please continue in [first time setup wiki page](https://wiki.kavitareader.com/en/guides/first-time-setup)

