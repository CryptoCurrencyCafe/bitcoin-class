
Instructions for instructors/TAs.
================================

To set up a node or a mining server you must:
###Install Dependencies

You are going to need git and mercurial.

####Install go
It's convient to add $GOPATH/bin to your systems PATH

####Install ntp 
This is reccomended, for maximum luck use ntpdate to force your clock to use what ntp reports.


###Get pointcoind
```bash
> go get -u -v github.com/PointCoin/pointcoind/...
```

###Join the Network

You have two options. Your machine can either mine or just act as a node, relaying blocks

As a *node*:
```bash
> pointcoind -d debug -a "54.84.178.186"
```

As a *miner*:
```bash
> pointcoind -d debug -a "54.84.178.186" -generate -miningaddr="Pdhgs7KhtwwNkLy6pRuCKpChWzbHn4Bkv2"
```

Note that the mining address is a throwaway. Nobody has the key to it. :)

