---
title: Raspberry Pi ➕ Docker ➕ minikube 🟰 your home Kubernetes cluster ⚗️
permalink: /your-home-kubernetes-cluster
date: 2023-04-04
categories: [Kubernetes]
tags: [kubernetes, minikube, docker, home-lab, laboratory]
---

## Selected technologies

Selected technologies for this project are:

| Area                | Selection                       | Version                |
|---------------------|---------------------------------|------------------------|
| Hardware            | [Raspberry Pi][RASP]            | 4 Model B with 8GB RAM |
| OS                  | [Ubuntu Server for ARM][UBUNTU] | 22.04.2 LTS (64-bit)   |
| Kubernetes platform | [minikube][MINIKUBE]            | 1.29.0                 |
| minikube driver     | [Docker][DOCKER]                | 23.0.2                 |

## Step one → prepare Raspberry Pi

Install Ubuntu Server on Raspberry Pi. Instructions can be found in [official Ubuntu documentation][UBU-ON-RASP]. Please remember to [enable SSH and set user and password][UBU-ON-RASP-ADV] during installation.

Connect to the Ubuntu server.

```bash
ssh [username]@[host]
```

## Step two → install Docker using the [convenience script][DOCKER-INST]

Execute [below command][ES-CURL-DOCK] to download the convenience script.

```bash
curl -L https://get.docker.com -o get-docker.sh
```

Execute downloaded script.

```bash
sudo sh get-docker.sh
```

Run [below command][ES-SU-UM-DOCK] to add your current user to the `docker` group.

```bash
sudo usermod -aG docker $USER
```

Then create a new shell execution environment with a new effective group identification.

```bash
newgrp docker
```

Finally, execute below command to verify 🩺 your new Docker installation.

```bash
docker run hello-world
```

## Step three → install minikube

Use [below command][ES-CURL-MINI] to download minikube.

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64
```

Install downloaded minikube.

```bash
sudo install minikube-linux-arm64 /usr/local/bin/minikube
```

Start 🚀 installed minikube.

```bash
minikube start --driver docker
```

Create an alias for convenience.

```bash
alias kubectl="minikube kubectl --"
```

Finally, time to verify 🩺 your local Kubernetes installation.

```bash
kubectl cluster-info
```

Congrats 🎉, your own Kubernetes cluster is all set up and ready to play with!

[RASP]: https://www.raspberrypi.com/products/raspberry-pi-4-model-b/?variant=raspberry-pi-4-model-b-8gb
[UBUNTU]: https://ubuntu.com/download/server/arm
[MINIKUBE]: https://minikube.sigs.k8s.io/docs/start/
[DOCKER]: https://docs.docker.com/get-started/
[UBU-ON-RASP]: https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi
[UBU-ON-RASP-ADV]: https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#3-using-advanced-options
[DOCKER-INST]: https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script
[HELM-INST]: https://helm.sh/docs/intro/install/
[ES-CURL-DOCK]: https://explainshell.com/explain?cmd=curl+-L+https%3A%2F%2Fget.docker.com+-o+get-docker.sh
[ES-SU-UM-DOCK]: https://explainshell.com/explain?cmd=sudo+usermod+-aG+docker+%24USER
[ES-CURL-MINI]: https://explainshell.com/explain?cmd=curl+-LO+https%3A%2F%2Fstorage.googleapis.com%2Fminikube%2Freleases%2Flatest%2Fminikube-linux-arm64
