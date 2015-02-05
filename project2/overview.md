This overview assumes you have successfully completed steps outlined in 
project 2, part 1, [initial setup](project2-part1.md).

### Run the PointCoin daemon
```
pointcoind -d debug -a "54.84.178.186" -u "[rpc username]" -P "[rpc password]"
```
|flag                       | explanation
|---------------------------|------------
|-d debug                   | enable debug mode
|-a "54.84.178.186"         | connect to another node with ip address
|-u "`[your rpc username]`" | username to interact with pointcoind over RPC
|-p "`[your rpc password]`" | password to interact with pointcoind over RPC


####View the hash of the pointcoin genesis block:
```
pointctl -u "[user]" -P "[pass]" getblockhash 0
```

####Use the output to view the contents of the genesis block:
```
pointctl -u "[user]" -P "[pass]" getblock [hash from above output]
```

####View the raw hex value of the coinbase transaction within the genesis block:
```
pointctl -u "[user]" -P "[pass]" getrawtransaction [tx hash from block output]
```

####Decode the raw hex and view contents of transaction:
```
pointctl -u "[user]" -P "[pass]" decoderawtransaction [hex output from getrawtransaction]
```

####Find the height of the pointcoin block chain:
```
pointctl -u "[user]" -P "[pass]" getblockcount
```

####Get the hash of the latest block:
```
pointctl -u "[user]" -P "[pass]" getbestblockhash
```

####View all unconfirmed transactions (this will likely  be empty):
```
pointctl -u "[user]" -P "[pass]" getrawmempool
```
 
####Now view some network information. The number of nodes you are conencted to:
```
pointctl -u "[user]" -P "[pass]" getconnectioncount
```

####Get information about your network peers:
```
pointctl -u "[user]" -P "[pass]" getpeerinfo
```

####Get the total mining power of the network (in SHA256 hashes per second):
```
pointctl -u "[user]" -P "[pass]" getnetworkhashps
```

####Get some information about the node running on your machine:
```
pointctl -u "[user]" -P "[pass]" getinfo
```