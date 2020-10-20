Installing Singularity
From: https://github.com/hpcng/singularity/blob/master/INSTALL.md
Since you are reading this from the Singularity source code, it will be assumed that you are building/compiling.

For full instructions on installation, check out our installation guide.

## Install system dependencies
You must first install development tools and libraries to your host. On Debian-based systems:

```bash
$ sudo apt-get update && \
  sudo apt-get install -y build-essential \
  libseccomp-dev pkg-config squashfs-tools cryptsetup
```


## Install Golang
This is one of several ways to install and configure golang. The CentOS/RHEL instructions above already installed it so this method is not needed there.

First, download the Golang archive to /tmp, then extract the archive to /usr/local.

**NOTE:** if you are updating Go from a older version, make sure you remove /usr/local/go before reinstalling it.

```bash
export VERSION=1.14.9 OS=linux ARCH=amd64  # change this as you need

wget -O /tmp/go${VERSION}.${OS}-${ARCH}.tar.gz https://dl.google.com/go/go${VERSION}.${OS}-${ARCH}.tar.gz && \
sudo tar -C /usr/local -xzf /tmp/go${VERSION}.${OS}-${ARCH}.tar.gz
```

Finally, set up your environment for Go:

```bash
echo 'export GOPATH=${HOME}/go' >> ~/.bashrc && \
echo 'export PATH=/usr/local/go/bin:${PATH}:${GOPATH}/bin' >> ~/.bashrc && \
source ~/.bashrc
```

## Install golangci-lint
This is an optional (but highly recommended!) step. To ensure consistency and to catch certain kinds of issues early, we provide a configuration file for golangci-lint. Every pull request must pass the checks specified there, and these will be run automatically before attempting to merge the code. If you are modifying Singularity and contributing your changes to the repository, it's faster to run these checks locally before uploading your pull request.

In order to install golangci-lint, you can run:

```bash
curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh |
sh -s -- -b $(go env GOPATH)/bin v1.21.0
```

This will download and install golangci-lint from its Github releases page (using version v1.21.0 at the moment).

Clone the repo
Golang is a bit finicky about where things are placed. Here is the correct way to build Singularity from source:

```bash
mkdir -p ${GOPATH}/src/github.com/sylabs && \
cd ${GOPATH}/src/github.com/sylabs && \
git clone https://github.com/sylabs/singularity.git && \
cd singularity
```

To build a stable version of Singularity, check out a release tag before compiling:

```bash
git checkout v3.6.3
```

## Compiling Singularity
You can build Singularity using the following commands:


```bash
cd ${GOPATH}/src/github.com/sylabs/singularity && \
./mconfig && \
cd ./builddir && \
make && \
sudo make install
```

And that's it! Now you can check your Singularity version by running:

```bash
singularity version
```

To build in a different folder and to set the install prefix to a different path:

```bash
./mconfig -b ./buildtree -p /usr/local
```