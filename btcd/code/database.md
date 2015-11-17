
package database/ldb

Location of
[Interface Definition Methods]
(http://godoc.org/github.com/btcsuite/btcd/database#Db)
in the individual files

#### block.go

* ExistsSha
* FetchBlockBySha
* FetchBlockHeightBySha
* FetchBlockHeaderBySha
* FetchBlockShaByHeight
* FetchHeightRange
* NewestSha
* FetchAddrIndexTip

#### tx.go

* InsertTx
* ExistsTxSha
* FetchTxByShaList
* FetchUnspentTxByShaList
* FetchTxBySha
* FetchTxsForAddr
* UpdateAddrIndexForBlock
* DeleteAddrIndex

#### leveldb.go

* InsertBlock
* DropAfterBlockBySha
* Sync
* RollbackClose
* Close
