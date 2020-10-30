# Docker installation

* to install the most recent version we recommend the following [Docker installation](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce)
* they also describe how to install docker on debian, or other distros
* in the following section we describe how to install docker on ubuntu

## For Ubuntu
* we are using this [installation guide](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce) but shorten it to the bare minimum for you
* so we skip a few steps that are not necessary

### Setting up the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository (via `apt update` and `apt upgrade`).

```bash
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

* Add Docker’s official GPG key:
* we skip the [verification here](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce)

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

**Note:** The lsb_release -cs sub-command below returns the name of your Ubuntu distribution, such as xenial. Sometimes, in a distribution like Linux Mint, you might need to change $(lsb_release -cs) to your parent Ubuntu distribution. For example, if you are using Linux Mint Tessa, you could use bionic. Docker does not offer any guarantees on untested and unsupported Ubuntu distributions.

* for x86_64 / amd64
```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

### Install Docker Engine

* install via

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
Verify that Docker Engine is installed correctly by running the hello-world image.

```bash
sudo docker run --rm hello-world
```

This command downloads a test image and runs it in a container. When the container runs, it prints an informational message and exits.

Docker Engine is installed and running. 

### Create docker group
* docker needs to run without sudo for nextflow so we need to add user that want to use docker to the docker group

* Create the docker group (should be already created after the installation)

```shell
sudo groupadd docker
```

* add a user to the docker group.

```shell
sudo usermod -aG docker $USER
```

* Restart
