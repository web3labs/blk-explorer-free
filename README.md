# Block Explorer for Quorum

## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) network. It is also compatible with [Ethereum](https://github.com/ethereum/go-ethereum) networks and ***may*** work with other forked variants


## Usage

Clone the repo, navigate to the cloned directory and run the instance with:

```bash
EXPLORER_IP=<server_ip> NODE_ENDPOINT=<node_endpoint> docker-compose -p <instance-name> up
```

The <instance-name> value should be unique for every new network being connected to.

N.B. Use the `-d` at the end to run the containers in the backgroud

N.B. Ommitting the `-p <instance-name>` may lead to inconsitant data shown in the explorer
 
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
