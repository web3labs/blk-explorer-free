# Block Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/Selection_051.png "Blk-Explorer-Free")

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
NODE_ENDPOINT=http://<node_endpoint> docker-compose -f <os>-docker-compose.yaml up
```
Append the `-d` argument to run the containers in the backgroud

You will be able to access the Explorer UI via:

* http://localhost:5000
 
### Localhost

You can set up the [7node](https://github.com/jpmorganchase/quorum-examples) example on your local machine and run the explorer with the following command.

#### Mac

```bash
NODE_ENDPOINT=http://docker.for.mac.host.internal:22000 docker-compose -f mac-docker-compose.yaml up -d
```

Use `docker.for.mac.host.internal` instead of `localhost` as described [here](https://docs.docker.com/docker-for-mac/networking/#use-cases-and-workarounds)

#### Windows

```cmd
set NODE_ENDPOINT=http://docker.for.win.host.internal:22000 && docker-compose -f win-docker-compose.yaml up
```

Use `docker.for.win.host.internal` instead of `localhost` as described [here](https://github.com/docker/for-win/issues/1638)

#### Linux

```bash
NODE_ENDPOINT=http://localhost:22000 docker-compose -f linux-docker-compose.yaml up -d
```

## Limitations

1. Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.
2. Viewing private transaction payloads on Quorum v2.0.0 (prior versions work) is not supported due to [this](https://github.com/jpmorganchase/quorum/issues/221) issue which should be fixed shortly.
3. Currently there is no guarantee that the information in the explorer is consistent with the blockchain as there is no mechanism to take into account reorgs.
