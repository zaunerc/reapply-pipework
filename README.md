# reapply-pipework

## Problem

When using [pipework](https://github.com/jpetazzo/pipework) to map physical network devices
into the network namespace of docker containers you will encounter the following problem.
Each time the docker container is restarted the mapped network device will not be available
anymore inside the container (it will be part of the default network namespace again).

## Solution

The `reapply-pipework` script is supposed to run periodically on a docker host.
It reapplies network settings to docker containers using [pipework](https://github.com/jpetazzo/pipework).
