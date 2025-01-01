---
title: 🗝️ Keycloak cookbook
date: 2024-05-23
categories: [Cookbook]
tags: [keycloak, docker, cookbook]
---

## Swiftly kick off local 🗝️ Keycloak `25.0.6` instance for prototyping

```shell
docker run \
    --detach \
    --publish 6100:8080 \
    --env KEYCLOAK_ADMIN=kc-admin \
    --env KEYCLOAK_ADMIN_PASSWORD=kc-admin-pass \
    quay.io/keycloak/keycloak:25.0.6 start-dev
```

Accessible at [localhost][KC-LOCALHOST]


[KC-LOCALHOST]: http://localhost:6100/
