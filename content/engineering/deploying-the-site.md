---
title: "Deploying the Site"
date: 2020-10-26T08:39:08-04:00
draft: false
---

Currently the deployment is a bit of a manual process. We're utilizing Elixir Releases inside of a docker container for dependency management and portability. 

No state is stored on the host machine besides a couple of environment variables.

### How to Deploy
1. `git pull`
2. `docker-compose build`
3. `docker-compose down && docker-compose up -d` 