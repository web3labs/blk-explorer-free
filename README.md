# Block Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/Selection_051.png "Blk-Explorer-Free")

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
NODE_ENDPOINT=http://<node_endpoint> docker-compose up
```

N.B. Use the `-d` at the end to run the containers in the backgroud
 
### Local machine

```bash
NODE_ENDPOINT=http://localhost:20010 docker-compose up -d
```

You will be able to access the explorer UI on the following endpoint:

* http://localhost:5000

## Limitations

1. Due to an annoying [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the explorer running at a time.
2. Viewing private transaction payloads on Quorum v2.0.0 (prior versions work) is not supported due to [this](https://github.com/jpmorganchase/quorum/issues/221) issue which should be patched up imminently.
