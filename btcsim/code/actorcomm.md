

*Notes about only the two core files actor and comm, all the methods listed here are called from within the file*

### actor.go

* queueUtxos [goroutine only]
* splitUtxos [goroutine only]
* simulateTx [goroutine only]

**sendRawTransaction**
is called by simulateTx and splitUtxos


### comm.go

* queueblocks [goroutine only]
* poolUtxos [goroutine only]
* Communicate [goroutine only]

**getUtxo** & **getActor**
are called by poolUxos
