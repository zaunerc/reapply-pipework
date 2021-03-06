# reapply-pipework

## Problem

When using [pipework](https://github.com/jpetazzo/pipework) to map physical network devices
into the network namespace of docker containers you will encounter the following problem.
Each time the docker container is restarted the mapped network device will not be available
anymore inside the container (it will be part of the default network namespace again).

## Solution

The `reapply-pipework` script is supposed to run periodically on a docker host.
It reapplies network settings to docker containers using [pipework](https://github.com/jpetazzo/pipework).

## Installation

1. Install the [pipework](https://github.com/jpetazzo/pipework) script to `/usr/local/sbin/`:
 1. `cd /usr/local/sbin/`
 1. `sudo wget https://raw.githubusercontent.com/jpetazzo/pipework/master/pipework`
 1. `sudo chmod a+x pipework`
1. Install the [reapply-pipework](https://github.com/zaunerc/reapply-pipework) script:
 1. Clone this git repository (e.g. `$ git clone https://github.com/zaunerc/reapply-pipework.git`)
 1. Install the [reapply-pipework](https://github.com/zaunerc/reapply-pipework) script by using the provided [install](https://github.com/zaunerc/reapply-pipework/blob/master/install) script. This installs the [reapply-pipework](https://github.com/zaunerc/reapply-pipework) script to `/usr/local/sbin/`.
 1. Configure the [reapply-pipework](https://github.com/zaunerc/reapply-pipework) script using the  `/usr/local/etc/reapply-pipework.conf` file.
