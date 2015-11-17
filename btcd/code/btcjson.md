
### Package btcd use of btcjson

* rpcserver
* rpcserverhelp
* rpcwebsocket
* server
* btcjson/btcws/*

### Key files not related to btcd

* cmdinfo.go
* cmdparse.go
* error.go
* help.go
* helpers.go
* jsonrpc.go
* jsonrpcerr.go
* register.go

## Public methods broken down by file

#### cmdinfo.go

[func CmdMethod(cmd interface{}) (string, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#CmdMethod)

[func MethodUsageFlags(method string) (UsageFlag, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#MethodUsageFlags)

[func MethodUsageText(method string) (string, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#MethodUsageText)

#### cmdparse.go

[func MarshalCmd(id interface{}, cmd interface{}) ([]byte, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#MarshalCmd)

[func UnmarshalCmd(r *Request) (interface{}, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#UnmarshalCmd)

[func NewCmd(method string, args ...interface{}) (interface{}, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#NewCmd)

#### help.go

[func GenerateHelp(method string, descs map[string]string, resultTypes ...interface{}) (string, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#GenerateHelp)

#### jsonrpc.go

[func MarshalResponse(id interface{}, result interface{}, rpcErr *RPCError) ([]byte, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#MarshalResponse)

[func NewResponse(id interface{}, marshalledResult []byte, rpcErr *RPCError) (*Response, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#NewResponse)

[func NewRequest(id interface{}, method string, params []interface{}) (*Request, error)]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#NewRequest)

[func NewRPCError(code RPCErrorCode, message string) *RPCError]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#NewRPCError)

[func (e RPCError) Error() string]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#RPCError.Error)

[func IsValidIDType(id interface{}) bool]
(http://godoc.org/github.com/btcsuite/btcd/btcjson/v2/btcjson#IsValidIDType)
