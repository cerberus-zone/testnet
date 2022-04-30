### Simple Testnet setup

A lot is assumed and left out here. We assume you are running a production validator and know all prerequisite steps.

#### Get Testnet genensis file

```
cd $HOME/.cerberus/config/

wget -O $HOME/.cerberus/config/genesis.json

https://raw.githubusercontent.com/cerberus-zone/testnet/main/genesis.json?token=GHSAT0AAAAAABUCZPUZZ32XRD7OXSNO3SG2YTMY3TQ
```

#### Setup peer
Just a single peer right now for testnet. Submit a PR if you would like to the be added to the peer list.

```
cd $HOME/.cerberus/config/

PEERS=$(curl https://raw.githubusercontent.com/cerberus-zone/cerberus_genesis/main/peers.txt | \
head -n 11 | sed 's/$/,/' | tr -d '\n' | sed '$ s/.$//'); sed "s/persistent_peers = \"\"/persistent_peers = \"$PEERS\"/" \
$HOME/.cerberus/config/config.toml -i
```

#### Running Testnet as a service

Reference the production here if you need steps to run the chain as a service <a href="https://www.cerberus.zone/running-a-validator.html#running-cerberus-as-a-service-systemd" target="_blank">here</a>.

#### Testnet $CRBRUS
Message anyone in the testnet-validator Discord channel to have testnet $CRBRUS sent to you.
