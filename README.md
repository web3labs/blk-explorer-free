# Blockchain Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/ExplorerCaption.png "Blk-Explorer-Free")


## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
NODE_ENDPOINT=http://<node_endpoint> docker-compose up
```
Append the `-d` argument to run the containers in the backgroud.

If you run docker(-compose) using `sudo` specify `sudo`'s `-E` option to
preserve the set environment variables.

You will be able to access the Explorer UI via:

* http://localhost:5000

If you want to run the Explorer on a remote server, change the host ip
so that the js requests from the UI are routed correctly:
```bash
NODE_ENDPOINT=http://<node_endpoint> HOST_IP=<IP of (docker) host running the containers> docker-compose up
```


To stop the containers use:

```bash
docker-compose down
```

To connect to a new network you need to delete one of the containers with:

```bash
docker rm blk-free-mongodb
```
 
### Local Quorum Networks

If you need to run a Quorum network locally, we recommend you use the following [4-node Quorum Docker image](https://github.com/blk-io/crux#4-node-quorum-network-with-crux), you can then start the Explorer via:

```bash
NODE_ENDPOINT=http://localhost:22001 docker-compose up
```

Alternatively there is a Vagrant version available [here](https://github.com/blk-io/quorum-examples).

## Limitations

 - Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.
