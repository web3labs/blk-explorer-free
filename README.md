# Block Explorer for Quorum

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) network. It is also compatible with [Ethereum](https://github.com/ethereum/go-ethereum) networks and ***may*** work with other forked variants


## Usage

```bash
cd ~/explorer-free
EXPLORER_IP=<server_ip> NODE_ENDPOINT=<node_endpoint> docker-compose -f free-docker-compose.yaml up -d
```

### Local machine

```bash
EXPLORER_IP=localhost NODE_ENDPOINT=http://${NODE_IP}:20010 docker-compose -f free-docker-compose.yaml up
```

You will be able to access the following endpoint:

* http://localhost:5000

### Cloud

1. Create a Linux VM with Ubuntu. 
2. Install Docker on VM. 
3. Proceed as with local machine instructions above, remember to set the EXPLORER_IP variable to the IP address of the VM in the cloud
4. Open ports 5000 and 8081 of the VM