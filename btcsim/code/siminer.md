
simulation.Start() is called from **main**

Inside simulation.Start() these methods are called: 

```
// Register for block notifications.
if err := node.client.NotifyBlocks(); err != nil {
  log.Printf("%s: Cannot register for block notifications: %v", node, err)
	return err
}

// Register for transaction notifications
if err := node.client.NotifyNewTransactions(false); err != nil {
	log.Printf("%s: Cannot register for transactions notifications: %v", node, err)
	return err
}
```

Then the notification handlers are called here:

```
actor.go:	     ntfnHandlers := &rpc.NotificationHandlers{
miner.go:	     ntfnHandlers := &rpc.NotificationHandlers{
simulation.go:   ntfnHandlers := &rpc.NotificationHandlers{
```

These are called in simulation.go and miner.go

[NotifyBlocks]
(http://godoc.org/github.com/btcsuite/btcrpcclient#Client.NotifyBlocks)

[OnBlockConnected]
(http://godoc.org/github.com/btcsuite/btcrpcclient#NotificationHandlers)

utxoQueue is the queue of utxos belonging to an actor

utxos are queued after a block is received and are dispatched
to their respective owner from com.poolUtxos

they are dequeued from simulateTx and splitUtxos
