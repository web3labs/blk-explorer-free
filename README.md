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
Append the `-d` argument to run the containers in the backgroud

You will be able to access the Explorer UI via:

* http://localhost:5000
 
### Example

```bash
NODE_ENDPOINT=http://localhost:20010 docker-compose up -d
```

## Limitations

1. Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.
2. Viewing private transaction payloads on Quorum v2.0.0 (prior versions work) is not supported due to [this](https://github.com/jpmorganchase/quorum/issues/221) issue which should be fixed shortly.
