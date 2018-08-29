# Block Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/ExplorerCaption.png "Blk-Explorer-Free")


## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
NODE_ENDPOINT=http://<node_endpoint> docker-compose -f docker-compose.yaml up
```
Append the `-d` argument to run the containers in the backgroud

You will be able to access the Explorer UI via:

* http://localhost:5000

To stop the containers use:

```bash
docker-compose -f docker-compose.yaml down
```

To connect to new network you need to delete one of the containers with:

```bash
docker rm blk-mongodb-free
```
 
### Localhost

You can set up the [7node](https://github.com/jpmorganchase/quorum-examples) example on your local machine and run the explorer with the following command.

#### Use for all OS

```bash
NODE_ENDPOINT=<node_endpoint> docker-compose -f blk-free-explorer.yaml up -d
```

## Limitations

1. Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.
