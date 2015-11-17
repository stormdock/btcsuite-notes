
#### blockHandler and msgChan

Everything gets placed on the **msgChan** and processed by the **blockHandler**.

```
type blockManager struct {
	msgChan chan interface{}
}
```

* NewPeer
* QueueTx
* QueueBlock
* QueueInv
* QueueHeaders
* DonePeer
* SyncPeer
* CheckConnectBlock
* CalcNextRequiredDifficulty
* FetchTransactionStore
* ProcessBlock
* IsCurrent
* Pause
