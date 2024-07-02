---
description: Part of the official docker documentation
---

# Docker & Docker compose

Information source: [docker documentation](https://docs.docker.com/engine/install/ubuntu/)

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

### Set up Docker's `apt` repository.

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### Install the Docker packages.

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Create the `docker` group.

```bash
sudo groupadd docker
```

Add your user to the `docker` group.

```bash
sudo usermod -aG docker $USER
```

Log out and log back in so that your group membership is re-evaluated or run the following command to activate the changes to groups:

```bash
newgrp docker
```

### Launch docker on system boot

Many modern Linux distributions use [systemd](https://systemd.io/) to manage which services start when the system boots. On Debian and Ubuntu, the Docker service starts on boot by default. To automatically start Docker and containerd on boot for other Linux distributions using systemd, run the following commands:

```bash
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```
