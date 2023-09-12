# `gentx`

To generate your `gentx` run the following command with the launch genesis file at `~/.stchaind/config/genesis.json`:

```
$ stchaind gentx <wallet_name> <amount_to_delegate> \
  --moniker <moniker>
  --home </path/to/home/dir> \
  --keyring-backend <os|file|pass>
  --min-self-delegation <min_self_delegation> \
  --commission-rate <commission_rate> \
  --commission-max-rate <commission_max_rate> \
  --commission-max-change-rate <commission_max_change_rate> \
  --pubkey <consensus_pubkey> \
  --chain-id "stratos-1" \
  --output-document <moniker>.json
```

This will produce a file in the `~/.stchaind/config/gentx/` folder that has a name with the format `gentx-<node_id>.json`. The content of the file should have a structure as follows:

```json
{
  "body":{
    "messages":[
      {
        "@type":"/cosmos.staking.v1beta1.MsgCreateValidator",
        "description":{
          "moniker":"<moniker>",
          "identity":"",
          "website":"",
          "security_contact":"",
          "details":""
        },
        "commission":{
          "rate":"0.100000000000000000",
          "max_rate":"0.200000000000000000",
          "max_change_rate":"0.010000000000000000"
        },
        "min_self_delegation":"1",
        "delegator_address":"st1hr7uhnene6d3rtk8fruer927wyae60qdzc9g6p",
        "validator_address":"stvaloper1hr7uhnene6d3rtk8fruer927wyae60qd45vgx2",
        "pubkey":{
          "@type":"/cosmos.crypto.ed25519.PubKey",
          "key":"C9rzsTtvhn1bsXgEsqgLsFsEthAi1rs9kaqAsKKYCzE="
        },
        "value":{
          "denom":"wei",
          "amount":"10000000000000000000"
        }
      }
    ],
    "memo":"<node_id>@<ip>:26656",
    "timeout_height":"0",
    "extension_options":[

    ],
    "non_critical_extension_options":[

    ]
  },
  "auth_info":{
    "signer_infos":[
      {
        "public_key":{
          "@type":"/stratos.crypto.v1.ethsecp256k1.PubKey",
          "key":"Apm12YRlaJiuL9ab75C6tKgLF2X9bK+TBTGxfmvY2uxq"
        },
        "mode_info":{
          "single":{
            "mode":"SIGN_MODE_DIRECT"
          }
        },
        "sequence":"0"
      }
    ],
    "fee":{
      "amount":[

      ],
      "gas_limit":"200000",
      "payer":"",
      "granter":""
    }
  },
  "signatures":[
    "mJCYmx9OqRZIizyqsOnvY3e8BipgwCJVboTxMN8wC+ZEK/YXCBNjDTXGlKVcxL7MJn/b6jlFeQqjoRhmGsn14wA="
  ]
}
```

To submit your `gentx` for inclusion in genesis, open a pull request against this repository and place the contents in a file `/gentx/<moniker>.json`.

__**NOTE**__: If you would like to override the memo field use the `--ip` and `--node-id` flags for the `stchaind gentx` command above.

full steps to create the gentx
```
./stchaind init <node_moniker> --chain-id 'stratos-1' --home .
./stchaind keys add <wallet_name> --keyring-backend file --hd-path "m/44'/606'/0'/0/0" --home .
./stchaind add-genesis-account <wallet_name> 90stos --home . --keyring-backend file
```