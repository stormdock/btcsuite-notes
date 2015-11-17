
Logging in btcd is supported by:

https://github.com/cihub/seelog

which was forked and then a bit more functionality was added:

https://github.com/btcsuite/btclog

Out of the box the following subsystem loggers show logging information
in the normal course of running the node.

{AMGR, BMGR, BTCD, DISC, RPCS, SRVR}

see **config.go** for more details on logging

#### Examples of starting up with logging

```
alias rbgo='./bin/btcd -u rpcuser -P rpcpass'
alias rbgo1='./bin/btcd -u rpcuser -P rpcpass -d=PEER=debug'
alias rbgo1a='./bin/btcd -u rpcuser -P rpcpass -d=PEER=trace'
alias rbgo2='./bin/btcd -u rpcuser -P rpcpass -d=BMGR=trace'
alias rbgo3='./bin/btcd -u rpcuser -P rpcpass -d=BMGR=trace,BCDB=trace'
alias rbgo4='./bin/btcd -u rpcuser -P rpcpass -d=BMGR=trace,RPCS=trace'
```
