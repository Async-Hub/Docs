---
layout: default
title: Docker Cheat Sheet
parent: Docker
grand_parent: Windows Subsystem for Linux
nav_order: 1
has_children: false
permalink: wsl/docker/cheat-sheet
---

## Docker Cheat Sheet

How to:

list images
```powershell
docker images
```

remove an image

```powershell
docker rmi "name or ID"
```

see all containers
```powershell
docker -ps -a
```

run a container
```powershell
docker run -d "name or ID"
```

restart a container
```powershell
docker restart "name or ID"
```

stop a container
```powershell
docker stop "name or ID"
```

remove a container
```powershell
docker rm
"name or ID"
```

onnect to a container
```powershell
docker exec -it "container name" /bin/bash
```