This overview assumes you have successfully completed steps outlined in 
Project 2, Part 1, [initial setup](project2-part1.md).

##Overview

The [developers](https://conformal.com/) of btcsuite divided their full node implemenation into 
seperate packages based upon their function for efficiency, safety, and intuitive development.  You 
can read more about that decision [here](https://blog.conformal.com/btcd-not-your-moms-bitcoin-daemon/).
For now there are three binaries you need to be familiar with:

+ `pointcoind`
+ `wallet`
+ `pointctl`

`pointcoind` contains the fundamental functions of a pointcoin [full node](https://en.bitcoin.it/wiki/Full_node).  
`wallet` contains the functions to interface with your pointcoin private keys.  
`pointctl` is the command line interface to interact with the RPC functions within pointcoind and wallet.

###Overview of this Overview
1. We will configure `pointcoind`, then download the pointcoin block chain
2. We will daemonize `pointcoind`
3. We will configure `wallet`
4. We will daemonize `wallet`
5. We will configure `pointctl`, then play around with its' functions


## pointcoind
### Pointcoin Configuration File
Create a file in your home directory titled `pointcoind.conf`.  Within we will define the RPC username and
the RPC password pointcoind will use and some initial peers for pointcoind to connect to.  An example of an elaborate 
pointcoin.conf file can be found [here](https://github.com/PointCoin/pointcoind/blob/master/sample-btcd.conf).

Add these four lines to the pointcoind.conf file:
```
rpcuser=[add_your_username_here]
rpcpass=[add_your_password_here]
addpeer=54.84.178.186
addpeer=54.152.35.87
addpeer=75.75.4.23
```



### Run the pointcoin daemon
```
pointcoind -d debug -a "
```
|flag                       |description
|:--------------------------|:-----------
|-d debug                   | enable debug mode
|-a "54.84.178.186"         | connect to another node with ip address


|command                                      |description
|:--------------------------------------------|:----------
|`pointctl getblockhash 0`                    |Hash of the pointcoin genesis block
|`pointctl getblock [block 0 hash]`           |Contents of the genesis block
|`pointctl getrawtransaction [tx hash]`       |Dump raw hex of some transaction
|`pointctl decoderawtransaction [tx raw hex]` |Decodes raw hex of tx into readable format
|`pointctl getblockcount`                     |Height of the pointcoin block chain
|`pointctl getbestblockhash`                  |Hash of the highest block in chain
|`pointctl getrawmempool`                     |All unconfirmed transactions (likely to be empty)
|`pointctl getconnectioncount`                |Number of peers your node is connected to
|`pointctl getpeerinfo`                       |Information about fellow peers
|`pointctl getnetworkhashps`                  |The network hash rate (sha256 hashes / second)
|`pointctl getinfo`                           |Information about the local node


