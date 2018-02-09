# Block Explorer for Quorum and Ethereum

Inline-style: 
![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/Selection_051.png "Blk-Explorer-Free")

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
EXPLORER_IP=<server_ip> NODE_ENDPOINT=<node_endpoint> docker-compose -p <instance-name> up
```

The <instance-name> value should be unique for every new network being connected to.

N.B. Use the `-d` at the end to run the containers in the backgroud

N.B. Omitting the `-p <instance-name>` may lead to inconsitant data shown in the explorer
 
### Local machine

```bash
EXPLORER_IP=localhost NODE_ENDPOINT=http://localhost:20010 docker-compose -p localchain up -d
```

You will be able to access the explorer UI on the following endpoint:

* http://localhost:5000

### Cloud

1. Create a Linux VM with Ubuntu. 
2. From the created VM:
	    1. Install Docker. 
	    2. Proceed as with local machine instructions above, remember to set the EXPLORER_IP variable to the IP address of the VM in the cloud
	    3. Open ports 5000 and 8081 on the VM
		
You will be able to access the explorer UI on the following endpoint:

* http://<VM-IP|FQDN>:5000

## Limitations

1. Due to an annoying [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the explorer running at a time.
2. Viewing private transaction payloads on Quorum v2.0.0 (prior versions work) is not supported due to [this](https://github.com/jpmorganchase/quorum/issues/221) issue which should be patched up imminently.
