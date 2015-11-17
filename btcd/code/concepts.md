
#### AddrIndex

This is an important high level concept which is supported by 3
[database interface]
(http://godoc.org/github.com/btcsuite/btcd/database#Db)
methods including :

* UpdateAddrIndexForBlock
* DeleteAddrIndex
* FetchAddrIndexTip

#### ProcessBlock

This is an important highlevel method which abstracts away alot of the lower
level block procesing infrastructure.

To discover the block method chain from the bottom start with *InsertBlock*
and work yourself up through the method hierarchy until you get to ProcessBlock.

see ProcessBlock for further details in {blockmanager, rpcserver}

* blockchain/process/ProcessBlock
* blockchain/accept/maybeAcceptBlock
* blockchain/chain/connectBestChain
* blockchain/chain/connectBlock
* database/ldb/leveldb/InsertBlock
