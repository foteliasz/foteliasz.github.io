---
title: Devcontainer CLI cookbook
date: 2024-06-27
categories: [Cookbook]
tags: [Devcontainer, cookbook]
---

## Installation

[Reference](https://code.visualstudio.com/docs/devcontainers/devcontainer-cli#_installation)

## Available Dev Container Templates

[Reference](https://containers.dev/templates)

## Setting up new Python project

Create configuration directory

```shell
devcontainer templates apply ^
    --workspace-folder . ^
    --template-id ghcr.io/devcontainers/templates/python:3.1.0
```

Spinning up new devcontainer

```shell
devcontainer up
```
