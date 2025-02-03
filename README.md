# mainnet
 The genesis files for Stratos mainnet 

[genesis_base.json](genesis%2Fgenesis_base.json) contains the basic configuration for Stratos Chain Mainnet.

[tropos_rewards.json](accounts%2Ftropos_rewards.json) contains the Tropos incentive testnet final rewards.

[burned_erc20.json](accounts%2Fburned_erc20.json) contains all burned erc20 STOS which will be updated on September 13

[genesis.json](genesis%2Fgenesis.json) the final genesis file that will be used to launch the mainnet

[config.toml](config.toml) example config file for network connection.

### ~~Create your validator from genesis block~~ (this step has passed)

~~create a gentx and make a pull-request to be included in the genesis [read more](gentx%2FREADME.md)~~

### September 14, 2023  Finalize Genesis File for Mainnet

On the specified date, we will aggregate all gentx and accounts/balances to finalize the genesis file for Stratos Chain 
Mainnet with chain id `stratos-1`

the final gensis file [genesis.json](genesis%2Fgenesis.json)

### September 21, 2023  Stratos Chain Mainnet Launch

If your validator is included in the final genesis, please launch your validator node on the date before Sep 21, 2023, 14:00 UTC 

seed node info 
```
seeds = "cdbd7ce27584e699d9b9e6d72a1551666c750e4d@35.86.41.142:26656,ce225e67f7a383b50c91aeb902a86dd3ecb70d65@34.84.212.13:26656"
```

### After Stratos Chain Release v0.12.0 
- Use [genesis.json](genesis/genesis.json) if you are using [state sync](https://docs.thestratos.org/docs-stratos-chain/how-to-start-with-state-sync/) to start the node after v0.12.0 update
- Use [genesis_v0.11_launch.json](genesis/genesis_v0.11_launch.json) if you start the chain from block height 0 and try to synchronize all blocks

