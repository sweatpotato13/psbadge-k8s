<h1>psbadge-k8s</h1>

Skaffold config for psbadge

<!-- TOC -->
- [Description](#description)
- [Installation](#installation)
- [How it works](#how-it-works)
<!-- /TOC -->

---
## Description

`psbadge-k8s` is a skaffold config for setting up k8s environment easily

You need `Skaffold`, `Minikube`, `Kubectl`

`Minikube` can be replaced `docker-desktop` or any other k8s clusters

![ss](https://i.imgur.com/NYDhQhi.png)

## Installation

### 1. Skaffold

#### 1.1 Linux
```bash
# For Linux AMD64
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-linux-amd64 && \
sudo install skaffold /usr/local/bin/
```

```bash
# For Linux ARM64
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-linux-arm64 && \
sudo install skaffold /usr/local/bin/
```

#### 1.2 Mac OS
```bash
# For macOS on AMD64
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-darwin-amd64 && \
sudo install skaffold /usr/local/bin/
```

```bash
# For macOS on ARM64
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-darwin-arm64 && \
sudo install skaffold /usr/local/bin/
```

#### 1.3 Google Cloud
Make sure your gcloud installation and the components are up to date:

`gcloud components update`

Then, install Skaffold:

`gcloud components install skaffold`


### 2. Kubectl

#### 2.1 Linux
Update the apt package index and install packages needed to use the Kubernetes apt repository:

```bash
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
```
Download the Google Cloud public signing key:

```bash
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
```
Add the Kubernetes apt repository:

```bash
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```
Update apt package index with the new repository and install kubectl:

```bash
sudo apt-get update
sudo apt-get install -y kubectl
```

#### 2.2 Mac OS
```bash
brew install kubectl 
```

## How it works

### 1. Setup configmap

rename configmap.example to configmap and fill out .yaml files

### 2. Run skaffold

in terminal run command `skaffold run`