# go-poll-endpoint is an Unix util to poll an endpoint

This small unix tool aims to make it easy to check if an http endpoint
is reachable. It waits for a http endpoint to be reachable and return
with "http.StatusOK".

### Install

```sh
go install github.com/ipfs/go-poll-endpoint
```

### Usage:

```
> go-poll-endpoint --help
Usage of go-poll-endpoint:
  -ep string
        which http endpoint path to hit (default "/version")
  -host string
        the multiaddr host to dial on (default "/ip4/127.0.0.1/tcp/5001")
  -tout duration
        how long to wait between attempts (default 1s)
  -tries int
        how many tries to make before failing (default 10)
  -v    verbose logging
> go-poll-endpoint -v
19:11:45.285 DEBUG pollEndpoi: starting at %s, tries: %d, timeout: %s, url: %s2017-09-23 19:11:45.285640066 +0200 CEST m=+0.001535252 10 1s {http  <nil> 127.0.0.1:5001 /version  false  } go-poll-endpoint.go:57
19:11:45.286 DEBUG pollEndpoi: ok -  endpoint reachable with 10 tries remaining, took 565.206µs go-poll-endpoint.go:63
> go-poll-endpoint
> echo $?
0
```

### License

MIT
