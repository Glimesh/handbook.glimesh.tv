---
title: "Deploying the Site"
date: 2020-10-26T08:39:08-04:00
draft: false
---

The Glimesh.tv deployments are now handled by running the ansible scripts found in [Glimesh/ops](https://github.com/Glimesh/ops/tree/main/ansible)

## Running Migrations
Currently, migrations are still ran very manually. After a web node is deployed you can run migrations on it by connecting to it via IEx.

```bash
iex --name "glimesh@dev" --cookie glimesh_secure_cookie --remsh glimesh@web1
...
iex(glimesh@web1)1>  Glimesh.Release.migrate()
```
