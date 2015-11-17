
The Servers Start method starts 7 services including

* listenHandler
* peer
* upnpUpdateThread
* rebroadcastHandler
* rpcServer
* cpuMiner
* addrIndexer

For more details see the Servers Start method code.

When the peerHandler inside the Server starts up it also goes ahead and starts

* addrManager
* blockManager

The server is located in **server.go**

#### listenHandler

In config.go there is a parameter called *activeNetParams* which sets up **cfg.Listeners**

The interface/port to listen for connections is a function of the type of network
{Mainnet, Testnet, Regnet, Simnet}
which is defined
[here]
(https://github.com/btcsuite/btcd/blob/master/chaincfg/params.go#L103)

in btcd.go the method **newServer** gets passed the **cfg.Listeners**

which sets up the **listenAddrs** which then get passed on to the

server.go method **newServer** shown here:

```
func newServer(listenAddrs []string, db database.Db, chainParams *chaincfg.Params) (*server, error)
```

calls a method

```
parseListeners(listenAddrs)
```

which eventually populates **s.listeners** via some IP4 / IP6 massaging.

when the server starts **listenHandler**, which gets run as a goroutine

```
func (s *server) listenHandler(listener net.Listener) {
```

grabs each item out of s.listeners...

**listenHandler** accepts incoming connections for the
server.  This is how the node communicates
with its Peers by setting up these connections in listenHandler.
