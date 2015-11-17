

#### peerHandler

The peerHandler gets started in the servers Start() method,
after this happens then other things happen.

#### To turn off the peer handler

Start up btcd with this command, this will allow you to talk to btcd
via the rpc commands but not worry about it running and getting more
data from the peers

```
alias rbgono='./bin/btcd -u rpcuser -P rpcpass --maxpeers=0'
```

#### handleAddPeerMsg

handleAddPeerMsg job is to start the individual peers.

**handleAddPeerMsg** gets called in the servers **peerHandler** method 3 times

but the only one that appears to really work most of the time and matter is the last one inside that method which is the default when one is needed and does not exist.

There is another call to the **handleAddPeerMsg** inside the server's method **handleQuery**
but I have actually not seen that one get fired off yet.


#### Overview 1 from code comments

peer provides a bitcoin peer for handling bitcoin communications.  The
overall data flow is split into 3 goroutines and a separate block manager.

The 3 goroutines are
* inHandler
* outHandler
* queueHandler

Inbound messages are read via the inHandler go routine and generally
dispatched to their own handler.  For inbound data-related messages such as blocks, transactions, and inventory, the data is passed on to the block
manager to handle it.

Outbound messages are queued via QueueMessage or QueueInventory.  
QueueMessage is intended for all messages, including responses to data such as blocks and transactions.  QueueInventory, on the other hand, is only intended for relaying inventory as it employs a trickling mechanism to batch the inventory together.  

The data flow for outbound messages uses two goroutines, queueHandler and outHandler.  The first, queueHandler, is used as a way for external entities (mainly block manager) to queue messages quickly regardless of whether the peer is currently sending or not.  It acts as the traffic cop between the external world and the actual goroutine which writes to the network socket.  In addition, the peer contains several functions which are of the form pushX, that are used to push messages to the peer.  Internally they use QueueMessage.
