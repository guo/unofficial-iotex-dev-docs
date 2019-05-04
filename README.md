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

