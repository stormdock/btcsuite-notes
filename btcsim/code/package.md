
Packages for btcsim are located
[here]
(http://godoc.org/github.com/btcsuite/btcsim?imports)

#### btcd.blockchain [comm.go]

```
coinbaseQueue: make(chan *btcutil.Tx, blockchain.CoinbaseMaturity),
```

#### btcd.btcjson [actor.go]

```
actor.go:				inputs := []btcjson.TransactionInput{{
actor.go:				inputs := []btcjson.TransactionInput{{
actor.go:func (a *Actor) sendRawTransaction(inputs []btcjson.TransactionInput, amounts map[btcutil.Address]btcutil.Amount) error {
```

#### btcd.chaincfg [comm.go]

```
&chaincfg.SimNetParams)
```

#### btcd.txscript [comm.go]

```
_, addrs, _, err := txscript.ExtractPkScriptAddrs(vout.PkScript,
```

#### btcd.wire

In many places

#### btcutil

In many places

#### btcrpcclient

The following files make RPC calls [actor, comm, miner, node, simulation]
