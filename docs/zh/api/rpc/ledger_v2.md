---
sidebarDepth: 4
---

# Ledger
:::tip 维护者
[lyd00](https://github.com/lyd00) && [vite-crzn](https://github.com/vite-crzn)
:::


## ledger_getUnreceivedBlocksByAddress

- **Parameters**:

  * `Address`: 账户地址
  * `uint64`: 页码, 从0开始
  * `uint64`: 每页大小

- **Return**:
  * `list<AccountBlock>` AccountBlock具体参考common_models_v2模块设计

- **Example**:

::: demo

```json tab:Request
{
    "jsonrpc": "2.0",
    "id": 2,
    "method": "ledger_getUnreceivedBlocksByAddress",
    "params": [
        "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10",
        0, 
        1
    ]
}
```

```json tab:Response
{
    "jsonrpc": "2.0",
    "id": 2,
    "result": [
        {
            "blockType": 2,
            "height": "556",
            "hash": "12ec1d40a6c7560ba77b3764977c609189299dcf63d6586b50374714d0b8e013",
            "prevHash": "9a6c20d7d7fc927d89de6d9991a7904330007751f9d7d24dec141cbdb8b9e5ef",
            "previousHash": "9a6c20d7d7fc927d89de6d9991a7904330007751f9d7d24dec141cbdb8b9e5ef",
            "accountAddress": "vite_f74d18fc6431cb9d813c62a47a9063c4b9488219dc22c2736d",
            "address": "vite_f74d18fc6431cb9d813c62a47a9063c4b9488219dc22c2736d",
            "publicKey": "yNr85NJpkjKoaobFuWwIcoIdQR+ZRPrG5myrBhGxG5Q=",
            "producer": "vite_f74d18fc6431cb9d813c62a47a9063c4b9488219dc22c2736d",
            "fromAddress": "vite_f74d18fc6431cb9d813c62a47a9063c4b9488219dc22c2736d",
            "toAddress": "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10",
            "fromBlockHash": "0000000000000000000000000000000000000000000000000000000000000000",
            "sendBlockHash": "0000000000000000000000000000000000000000000000000000000000000000",
            "tokenId": "tti_5649544520544f4b454e6e40",
            "amount": "16000000000000000000",
            "fee": "0",
            "data": "9HgjCQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABvBbWdOyAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAG8FtZ07IAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAbwW1nTsgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABvBbWdOyAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAG8FtZ07IAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAbwW1nTsgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABvBbWdOyAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAG8FtZ07IAAA=",
            "difficulty": "124419654",
            "nonce": "QxyYTRkNbco=",
            "signature": "sgcYMzD3L0KsEOeA9DckCPcOHeC7tTjiJdEcjS97guMKkOqHznnZ1naWkmDFJrtaNij1weRWMZ/27Y4rYc/DAw==",
            "quota": "0",
            "quotaByStake": "0",
            "quotaUsed": "38680",
            "totalQuota": "38680",
            "utUsed": "1.842",
            "logHash": null,
            "vmLogHash": null,
            "sendBlockList": null,
            "triggeredSendBlockList": null,
            "tokenInfo": {
                "tokenName": "VITE",
                "tokenSymbol": "VITE",
                "totalSupply": "1001186579383872099206960787",
                "decimals": 18,
                "owner": "vite_0000000000000000000000000000000000000004d28108e76b",
                "tokenId": "tti_5649544520544f4b454e6e40",
                "maxSupply": "115792089237316195423570985008687907853269984665640564039457584007913129639935",
                "ownerBurnOnly": false,
                "isReIssuable": true,
                "index": 0,
                "isOwnerBurnOnly": false
            },
            "confirmedTimes": "5345754",
            "confirmations": "5345754",
            "confirmedHash": "ab88339a58d481a3b132f5c3c69ba14ab5b31d77b8860985b17951e990e190b4",
            "firstSnapshotHash": "ab88339a58d481a3b132f5c3c69ba14ab5b31d77b8860985b17951e990e190b4",
            "receiveBlockHeight": null,
            "receiveBlockHash": null,
            "timestamp": 1562219525
        }
    ]
}
```


:::
## ledger_getUnreceivedBlocksInBatch

- **Parameters**:

  *  `PagingQueryBatch`- Object 具体字段类型如下
    |  名称  | 类型 |说明 |
    |:------------:|:-----------:|:-----:|
    | address |  string | 账户地址 |
    | pageNumber | uint64 | 页码, 从0开始 |
    | pageCount | uint64 | 每页大小 |

- **Return**:

  * `map<string Address, list<AccountBlock>>` AccountBlock具体参考common_models_v2模块 设计

- **Example**:

::: demo

```json tab:Request
{
    "jsonrpc": "2.0",
    "id": 2,
    "method": "ledger_getUnreceivedBlocksInBatch",
    "params": [
        [{
    		"address": "vite_00000000000000000000000000000000000000042d7ef71894", 
    		"pageNumber": 0 ,
    		"pageCount": 1
    	},{
    		"address": "vite_68c5edf9069efe327e01e925790d868c7f7972d815016cf18a", 
    		"pageNumber": 0 ,
    		"pageCount": 1
    	}
    	]
    ]	
}
```

```json tab:Response
{
    "jsonrpc": "2.0",
    "id": 2,
    "result": {
        "vite_68c5edf9069efe327e01e925790d868c7f7972d815016cf18a": [
            {
                "blockType": 2,
                "height": "170",
                "hash": "81a9a5e2747e28584db752a814bde0ee8894604df3707a9067e13f8297a090d5",
                "prevHash": "55e7088d3405aebed75c9e311303f52bbbc1827b11d86fd7840406e4f4bc42f8",
                "previousHash": "55e7088d3405aebed75c9e311303f52bbbc1827b11d86fd7840406e4f4bc42f8",
                "accountAddress": "vite_ba2ae946be1f56a8c83ce3e1d80a53d8137c264684d5dd7610",
                "address": "vite_ba2ae946be1f56a8c83ce3e1d80a53d8137c264684d5dd7610",
                "publicKey": "u7OxKqv0EqysClekERWf8FK3NgsEVnS6dq0Cu53en4o=",
                "producer": "vite_ba2ae946be1f56a8c83ce3e1d80a53d8137c264684d5dd7610",
                "fromAddress": "vite_ba2ae946be1f56a8c83ce3e1d80a53d8137c264684d5dd7610",
                "toAddress": "vite_68c5edf9069efe327e01e925790d868c7f7972d815016cf18a",
                "fromBlockHash": "0000000000000000000000000000000000000000000000000000000000000000",
                "sendBlockHash": "0000000000000000000000000000000000000000000000000000000000000000",
                "tokenId": "tti_5649544520544f4b454e6e40",
                "amount": "0",
                "fee": "0",
                "data": "6SXjDQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAbwW1nTsgAAA",
                "difficulty": null,
                "nonce": null,
                "signature": "8qNYBI2+rQOH6LmS+Skl5/lXCLaW3bZHVGfS8IFraol5LiGuukmjfzsiNGQTDpB7MN006K9VcCGE05eZKeyVAg==",
                "quota": "23448",
                "quotaByStake": "23448",
                "quotaUsed": "23448",
                "totalQuota": "23448",
                "utUsed": "1.117",
                "logHash": null,
                "vmLogHash": null,
                "sendBlockList": null,
                "triggeredSendBlockList": null,
                "tokenInfo": {
                    "tokenName": "VITE",
                    "tokenSymbol": "VITE",
                    "totalSupply": "1001186579383872099206960787",
                    "decimals": 18,
                    "owner": "vite_0000000000000000000000000000000000000004d28108e76b",
                    "tokenId": "tti_5649544520544f4b454e6e40",
                    "maxSupply": "115792089237316195423570985008687907853269984665640564039457584007913129639935",
                    "ownerBurnOnly": false,
                    "isReIssuable": true,
                    "index": 0,
                    "isOwnerBurnOnly": false
                },
                "confirmedTimes": "5257692",
                "confirmations": "5257692",
                "confirmedHash": "9c9a436d1d8b06c8a9955955890877b40c5e493c4054f59d36a3bfabf315772f",
                "firstSnapshotHash": "9c9a436d1d8b06c8a9955955890877b40c5e493c4054f59d36a3bfabf315772f",
                "receiveBlockHeight": null,
                "receiveBlockHash": null,
                "timestamp": 1562309573
            }
        ]
    }
}
```

:::


## ledger_getUnreceivedTransactionSummaryByAddress

- **Parameters**:

  *  `Address`- 账户地址

- **Return**:

  * `AccountInfo` AccountInfo具体参考common_models_v2模块设计

- **Example**:

::: demo

```json tab:Request
{
    "jsonrpc": "2.0",
    "id": 2,
    "method": "ledger_getUnreceivedTransactionSummaryByAddress",
    "params": [
        "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10"
    ]
}
```

```json tab:Response
{
    "jsonrpc": "2.0",
    "id": 2,
    "result": {
        "address": "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10",
        "blockCount": "6",
        "balanceInfoMap": {
            "tti_5649544520544f4b454e6e40": {
                "tokenInfo": {
                    "tokenName": "VITE",
                    "tokenSymbol": "VITE",
                    "totalSupply": "1001186579383872099206960787",
                    "decimals": 18,
                    "owner": "vite_0000000000000000000000000000000000000004d28108e76b",
                    "tokenId": "tti_5649544520544f4b454e6e40",
                    "maxSupply": "115792089237316195423570985008687907853269984665640564039457584007913129639935",
                    "ownerBurnOnly": false,
                    "isReIssuable": true,
                    "index": 0,
                    "isOwnerBurnOnly": false
                },
                "balance": "96000000000000000000",
                "transactionCount": "6"
            }
        }
    }
}
```
:::


## ledger_getUnreceivedTransactionSummaryInBatch

- **Parameters**:

  *  `list<Address>`- 账户地址列表

- **Return**:

  * `list<AccountInfo>` AccountInfo具体参考common_models_v2模块 设计

- **Example**:

::: demo

```json tab:Request
{
    "jsonrpc": "2.0",
    "id": 2,
    "method": "ledger_getUnreceivedTransactionSummaryInBatch",
    "params": [[
        "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10",
        "vite_68c5edf9069efe327e01e925790d868c7f7972d815016cf18a"
        ]
    ]
}
```

```json tab:Response
{
    "jsonrpc": "2.0",
    "id": 2,
    "result": [
        {
            "address": "vite_0b573f9d1fca7d830fc0d1552e3ff7b7f44455e38c8218fd10",
            "blockCount": "6",
            "balanceInfoMap": {
                "tti_5649544520544f4b454e6e40": {
                    "tokenInfo": {
                        "tokenName": "VITE",
                        "tokenSymbol": "VITE",
                        "totalSupply": "1001186579383872099206960787",
                        "decimals": 18,
                        "owner": "vite_0000000000000000000000000000000000000004d28108e76b",
                        "tokenId": "tti_5649544520544f4b454e6e40",
                        "maxSupply": "115792089237316195423570985008687907853269984665640564039457584007913129639935",
                        "ownerBurnOnly": false,
                        "isReIssuable": true,
                        "index": 0,
                        "isOwnerBurnOnly": false
                    },
                    "balance": "96000000000000000000",
                    "transactionCount": "6"
                }
            }
        },
        {
            "address": "vite_68c5edf9069efe327e01e925790d868c7f7972d815016cf18a",
            "blockCount": "1",
            "balanceInfoMap": {
                "tti_5649544520544f4b454e6e40": {
                    "tokenInfo": {
                        "tokenName": "VITE",
                        "tokenSymbol": "VITE",
                        "totalSupply": "1001186579383872099206960787",
                        "decimals": 18,
                        "owner": "vite_0000000000000000000000000000000000000004d28108e76b",
                        "tokenId": "tti_5649544520544f4b454e6e40",
                        "maxSupply": "115792089237316195423570985008687907853269984665640564039457584007913129639935",
                        "ownerBurnOnly": false,
                        "isReIssuable": true,
                        "index": 0,
                        "isOwnerBurnOnly": false
                    },
                    "balance": "0",
                    "transactionCount": "1"
                }
            }
        }
    ]
}
```

:::

## ledger_getVmlogsByFilter
根据参数查询历史日志。返回值按账户块高度从低到高排序。

- **Parameters**: 
  - 查询参数，同`subscribe_createVmlogFilter`，注意`fromHeight`和`toHeight`都填0时会查询整个账户链，可能会导致返回数据过多，最好指定明确的查询高度范围

- **Returns**:  
	- `Array<VmlogMessage>` 日志信息，同`subscribe_getChangesByFilterId`返回值
	
::: demo
```json tab:Request
{
	"jsonrpc": "2.0",
	"id": 1,
	"method": "ledger_getVmlogsByFilter",
	"params": [{
		"addressHeightRange":{
			"vite_8810e12ec2d4d61e7568cac25ebd5dd44735d36a405b94f1fa":{
				"fromHeight":"1",
				"toHeight":"10"
			}
		}
	}]
}
```
```json tab:Response
{
  "jsonrpc":"2.0",
  "id":1,
  "result": [
    {
      "vmlog": {
        "topics": [
          "28e6ea56797f4a1b22a1d1986cb6c22e80099ba8e4fd14d42accfaedfe5f6640"
        ],
        "data": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGQQurTFV9WklB2DRvsX8wLCgyoVomYHSCebb9Br/hQ+RAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABwYLIcJLnbQjGl+qeU7YWlTWwfsoF6mescP5xz2fDTEg="
      },
      "accountBlockHash": "e4917f357a4588ec1752797ee5516939f46078f5356b14422d4a9dfe45f88bf5",
      "accountBlockHeight": "10",
      "address": "vite_8810e12ec2d4d61e7568cac25ebd5dd44735d36a405b94f1fa",
      "removed": false
    }
  ]
}
```
:::