# Unofficial Development Document of Dev on IoTeX

## run IoTeX Node?
please refer to this guide: https://github.com/iotexproject/iotex-bootstrap

## your friend `ioctl`
Install ioctl by 
```
curl https://raw.githubusercontent.com/iotexproject/iotex-core/master/install-cli.sh | sh
```
You can set ioctl endpoint to your local server by 
```
ioctl config set endpoint localhost:14014 --insecure
```

Also, you can use it for interacting with mainnet or testnet
```
MainNet secure: api.iotex.one:443
MainNet insecure: api.iotex.one:80
TestNet secure: api.testnet.iotex.one:443
TestNet insecure: api.testnet.iotex.one:80
```
You can create a bash script to switch mainet and testnet
```
ioctl config set endpoint api.iotex.one:443 && echo 'switched to mainnet!'
```
and one to switch to testnet
```
ioctl config set endpoint api.testnet.iotex.one:443 && echo 'switched to testnet'
```
They are useful if you switch between mainnet and test frequently.

## using smart contract

use remix to compile your smart contract and find the bytecode, remove the first two chararacters `0x`. Then deploy using
```
#ioctl action deploy -s [signer] -l [gas limit] -b [bytecode]
```

To prepare to invoke individual functions, you need to deploy smart contract using VM on remix. 

Read contract. find bytecode of a read function.
```
#ioctl action read -s [signer] -l [gas limit] -b [bytecode]
```
Invoke contract. find the bytecode of a write function, then call through ioctl.
```
#ioctl action invoke -s [signer] -l [gas limit] -b [bytecode]
```

## debug
get into docker's runtime. since `v1.1`, IoTeX uses alphine linux https://alpinelinux.org/. It is a miminal linux image. You need to install software/pkg as needed.

```
sudo docker exec -it iotex /bin/sh
```

install `curl`

```
apk add --no-cache curl
```

install `golang`

```
apk add --no-cache golang
```

open `debug` logs
```
curl -X PUT -d '{"level":"debug"}'  localhost:9009/logging/global
```

open `info` logs
```
curl -X PUT -d '{"level":"info"}' localhost:9009/logging/global
```


  
