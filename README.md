# blockchain
## Introduction
The implementation already has mining, transaction, communication between nodes, and file persistence of blocks and transactions. This mining algorithm uses SHA-256. Bitcoin's algorithm is based on the block header + Nouce as a string. Simple blockchain simplifies the header information, but the mechanism and Bitcoin are constant.
The blockchain is stored locally in the file in JSON format. The generation of a block is related to the transaction information, so the block information is also stored when the block is stored.

## Requirement 
Ubuntu 18.04 LTS

Python 3.6+ (Ubuntu 18.04 LTS includes Python 3.6 installed)

This blockchain will run under different environment.

1 core 1G RAM

1 core 4G RAM

1 core 8G RAM

2 core 1G RAM

2 core 4G RAM

2 core 8G RAM

3 core 1G RAM

3 core 4G RAM

3 core 8G RAM

4 core 1G RAM

4 core 4G RAM

4 core 8G RAM

## Installation 

1. Install git
```
$ sudo apt install git
```
2. Git Clone
```
$ git clone https://github.com/nextbowen/blockchain.git
$ cd blockchain
```

## Usage

- Create account
```
$ python3 console account create
```
    The account information will be stored at ./blockchain/data/account
- Show all accounts
```
$ python3 console account get
```
- Show current accounts
```
$ python3 console account current
```
- Mining
```
$ python3 console miner start 3008
```
OR
```
$ python3 console miner start 127.0.0.1:3008
```
The mining block will stored at ./blockchain/data/blockchain
- Transaction transfer.   
```
$ python3 console tx transfer from_address to_address amount
```
- Transaction list.   
```
$ python3 console tx list
```
- Blockchain shows.   
```
$ python3 console blockchain list
```

You might want to open all stored files on local machine if the VM is slow.
### Node Network
Copy the code resource to a new directory.While the miner before was running then:
```
$ cd {another_blockchain_directory}
$ python3 console node add 3008 
$ python3 console node run 3009
```
When a new block mined , block and transactions will broadcast to other nodes.
- Add a node that will broadcast to
```
$ python3 console node add [ip:port]
```
- Show all nodes that will broadcast to
```
$ python3 console node list
```

## Blockchain block

Blockchain-python simplified block structure, a blockchain-python block data is as follows:
```
{
	"index": 7,
	"timestamp": 1528972070,
	"tx": [
        "b959b3d2099ca304c67087edbf05b79d1f2501b1f407df5e51a1a8c22bb3334d",
        "613e4af7266e01ea338d30681ef606bad26e4cdfa4ec7a6f431e22420c8291fd",
        "be7095a764cb241606a67c9064bc8dbc2da2370d49459bd492473ea5ce304cb3"
    ],
	"previous_block": "00003e17e04d9c9d2c2f5629de20bda58f59af36417a7e50eb77a74a028b026a",
	"nouce": 11063,
	"hash": "00006805c75d0db1685616d9ea5730f6203eda744a16fcc78ef1f3c244083ea4"
}
```
The calculation of block hash is roughly the same as that of Bitcoin. Our difficulty setting is relatively low, so the hash in front of this block has only 4 zeros. The number of zeros is the difficulty of mining.

