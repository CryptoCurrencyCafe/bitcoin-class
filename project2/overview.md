This overview assumes you have successfully completed steps outlined in 
project 2, part 1, [initial setup](project2-part1.md).

### Run the PointCoin daemon
```
pointcoind -d debug -a "54.84.178.186" -u "[rpc username]" -P "[rpc password]"
```
|flag                       | description
|---------------------------|------------
|-d debug                   | enable debug mode
|-a "54.84.178.186"         | connect to another node with ip address
|-u "`[your rpc username]`" | username to interact with pointcoind over RPC
|-p "`[your rpc password]`" | password to interact with pointcoind over RPC


|command                                                              |description
|:--------------------------------------------------------------------|:----------
|'pointctl -u "[user]" -P "[pass]" getblockhash 0'                    |Retrieves the hash of the pointcoin genesis block
|'pointctl -u "[user]" -P "[pass]" getblock [block 0 hash]'           |Retrieves contents of the genesis block
|'pointctl -u "[user]" -P "[pass]" getrawtransaction [tx hash]'       |Dump raw hex of some transaction
|'pointctl -u "[user]" -P "[pass]" decoderawtransaction [tx raw hex]' |Decodes raw hex into readable format
|'pointctl -u "[user]" -P "[pass]" getblockcount'                     |Find the pointcoin block chain height
|'pointctl -u "[user]" -P "[pass]" getbestblockhash'                  |Get the hash of the highest block in chain
|'pointctl -u "[user]" -P "[pass]" getrawmempool'                     |View all unconfirmed transactions (this will likely be empty)
|'pointctl -u "[user]" -P "[pass]" getconnectioncount'                |View number of peers your node is connected to
|'pointctl -u "[user]" -P "[pass]" getpeerinfo'                       |View information about those peers
|'pointctl -u "[user]" -P "[pass]" getnetworkhashps'                  |Find the network hash rate (sha256 hashes / second)
|'pointctl -u "[user]" -P "[pass]" getinfo'                           |Information about the node running on your machine


