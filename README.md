# pyLoad

#### Table of Contents

1. [Overview](#overview)
2. [Container Description - What the container does and why it is useful](#container-description)
3. [Setup - The basics of getting started with monit](#setup)
4. [Usage - Configuration options and additional functionality](#usage)
    * [Basic Running](#basic-running)
    * [Configuration](#configuration)
    * [Restart pyLoad](#restart-pyload)
5. [Contributors](#contributors)

## Overview

Docker container with pyLoad installed.

## Container Description

This container embeds [pyLoad](http://pyload.org/) v0.4.9 on a [Debian Jessie](https://www.debian.org/releases/jessie/).
HTTPs Dashboard : 
The web interface is listening on 8000 port.
The core is listening on 7227 port for remote interfaces.
The SSL option is enabled on both ports.

## Setup

```sh
docker pull flosox/pyload:0.4.9
```

## Usage

### Basic Running

```sh
docker run -d -P --name pyload flosox/pyload:0.4.9
```

### Configuration

#### Add a user

Execute a Shell on your container

```sh
docker exec -it pyload bash
```

On this Shell, execute ```pyLoadCore -u``` and follow the instructions.

#### Link Downloads directory to host directory

```sh
docker run -d -v <host-directory>:/root/.pyload/Downloads -P --name pyload flosox/pyload:0.4.9
```

Read More : https://docs.docker.com/userguide/dockervolumes/

### Restart pyLoad

To restart pyLoad, you just have to restart the container.

```sh
docker restart pyload
```

## Contributors

The list of contributors can be found at: https://github.com/floSoX/docker-pyload/graphs/contributors
