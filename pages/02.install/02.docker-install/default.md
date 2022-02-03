---
title: 'Docker Install'
---

### Introduction

The Kavita team does offer an official Docker image which is automatically updated based on changes to [GitHub](https://github.com/Kareadita/Kavita).

#### 1. Kavita on Docker Hub

[Kizaing/KavitaDocker](https://hub.docker.com/r/kizaing/kavita)

#### 2. Docker Install


Running your Kavita server in docker is super easy! You can run the `:latest` stable version with bind mounts using this command:
```
docker run --name kavita -p 5000:5000 \
-v /your/manga/directory:/manga \
-v /kavita/data/directory:/kavita/config \
--restart unless-stopped \
-e TZ=Your/Timezone \
-d kizaing/kavita:latest
```
You can also run it via the docker-compose file:
```
version: '3.9'
services:
    kavita:
        image: kizaing/kavita:latest
        volumes:
            - ./manga:/manga
            - ./data:/kavita/config
        environment:
            - TZ=Your/Timezone
        ports:
            - "5000:5000"
        restart: unless-stopped
```
You don't need to call it manga, you can name it anything that works for you. Kavita supports more than just Manga.

!  **Note**: Kavita is under heavy development and is being updated all the time, so the tag for current builds is `:nightly`. The `:latest` tag will be the latest stable release.

### 3. Setup Kavita
Open http://localhost:5000 and setup your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.

### 4. View Kavita

Browse to http://localhost:5000 to start using Kavita from any device inside your network.