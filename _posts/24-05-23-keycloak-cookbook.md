---
title: Keycloak cookbook
date: 2024-05-23
categories: [Cookbook]
tags: [keycloak, docker, home-lab, diy]
---

## Swiftly kick off local 🗝️ Keycloak `21.1.2` instance for prototyping

```shell
docker run \
    --detach \
    --publish 6100:8080 \
    --env KEYCLOAK_ADMIN=admin \
    --env KEYCLOAK_ADMIN_PASSWORD=kc-admin-pass \
    quay.io/keycloak/keycloak:21.1.2 start-dev
```

Accessible at [localhost][KC-LOCALHOST]


[KC-LOCALHOST]: http://localhost:6100/
