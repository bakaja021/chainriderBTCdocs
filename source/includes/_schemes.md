
# Data Objects

<a id="divider">

<h2 id="tocTokenUsage">Token Usage</h2>

<a id="schemetokenusageobject"></a>

|Name|Type|Description|
|---|---|---|
|message|JSON|Message object containing all relevant token usage data.|
|hour|[Usage object](#schemeusageobject)|Provides info regarding API usage for current hour|
|day|[Usage object](#schemeusageobject)|Provides info regarding API usage for current day|
|forward|[Usage object](#schemeusageobject)|Provides info regarding payment forward API usage for current month|

> Example

```json
{
  "message":{
      "hour":{
          "usage":2,
          "limit":300,
          "time_left":1857
      },
      "day":{
          "usage":2,
          "limit":3000,
          "time_left":34257
      },
      "forward":{
          "usage":0,
          "limit":3,
          "time_left":1675857
      }
  }
}
```

<h2 id="tocUsageObject">UsageObject</h2>

<a id="schemeusageobject"></a>

|Name|Type|Description|
|---|---|---|
|usage|Integer|Number of used API calls within corresponding period|
|limit|Integer|Total number of available API calls within corresponding period|
|time_left|Integer|Time left in seconds before the counting is restarted|

> Example

```json
{
  "usage":2,
  "limit":300,
  "time_left":1857
}
```

<h2 id="tocBlockchainInfoObject">BlockchainInfoObject</h2>

<a id="schemeblockchaininfoobject"></a>

|Name|Type|Description|
|---|---|---|
|info|JSON|Info object|
|version|Integer|Bitcore version|
|insightversion|String|Insight API version|
|protocolversion|Integer|Blockchain protocol version|
|blocks|Integer|Number of blocks|
|timeoffset|Integer|Time offset|
|connections|Integer|Number of connections to other nodes|
|proxy|String|Proxy used for connecting|
|difficulty|Float|Current mining difficulty|
|testnet|Boolean|Is it the testnet version of the blockchain|
|relayfee|Float|Minimum relay fee in BTC|
|errors|String|Error description|
|network|String|Blockchain type ENUM {"livenet", "testnet"}|

<a id="divider"></a>

> Example

```json
{
    "info":
    {
        "version":120203,
        "insightversion":"0.6.0",
        "protocolversion":70208,
        "blocks":894442,
        "timeoffset":0,
        "connections":8,
        "proxy":"",
        "difficulty":91708039.52534924,
        "testnet":false,
        "relayfee":0.00001,
        "errors":"",
        "network":"livenet"
    }
}
```

<h2 id="tocBlockchainDifficultyObject">BlockchainDifficultyObject</h2>

<a id="schemeblockchaindifficultyobject"></a>

|Name|Type|Description|
|---|---|---|
|difficulty|Float|Current mining difficulty|

> Example



```json
{
    "difficulty":91708039.52534924
}
```

<h2 id="tocBlockchainBestBlockObject">BlockchainBestBlockObject</h2>

<a id="schemeblockchainbestblockobject"></a>

|Name|Type|Description|
|---|---|---|
|bestblockhash|String (HEX)|Hash of the best block|

<a id="divider"></a>

> Example

```json
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

<h2 id="tocBlockchainLastBlockObject">BlockchainLastBlockObject</h2>

<a id="schemeblockchainlastblockobject"></a>

|Name|Type|Description|
|---|---|---|
|syncTipHash|String (HEX)|Hash of the block up to which the sync has been done|
|lastblockhash|String (HEX)|Hash of the last block|

<a id="divider"></a>

> Example

```json
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

<h2 id="tocBlockchainDataSyncObject">BlockchainDataSyncObject</h2>

<a id="schemeblockchaindatasyncobject"></a>

|Name|Type|Description|
|---|---|---|
|status|String|Sync status|
|blockChainHeight|Integer|Current blockchain height|
|syncPercentage|Integer|Sync status as persentage |
|height|Integer|Blockchain height (last block index)|
|error|String|Error description|
|type|String|Sync type|

<a id="divider"></a>

> Example

```json
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```

<h2 id="tocVoteCountObject">VoteCountObject</h2>

<a id="schemevotecountobject"></a>

|Name|Type|Description|
|---|---|---|
|AbsoluteYesCount|Integer|Number of Absolute Yes Votes|
|YesCount|Integer|Number of Yes Votes|
|NoCount|Integer|Number of No Votes|
|AbstainCount|Integer|Number of Abstain Votes|

<a id="divider"></a>

> Example

```json
{
    "AbsoluteYesCount":60,
    "YesCount":89,
    "NoCount":29,
    "AbstainCount":0
}
```

<h2 id="tocBlockObject">BlockObject</h2>

<a id="schemeblockobject"></a>

|Name|Type|Description|
|---|---|---|
|hash|String (HEX)|Hash of the block|
|size|Integer|Size of the block|
|height|Integer|Block height in the chain|
|version|Integer|Block version number|
|merkleroot|String (HEX)|256-bit hash based on all of the transactions in the block |
|tx|Array of Strings|Array of tx hashes in the block|
|time|Integer|Timestamp as seconds since 1970-01-01T00:00 UTC|
|nonce|Integer|32-bit number (starts at 0)|
|bits|String (Hex)|Current target in compact format|
|difficulty|Float|Difficulty at which the block was mined|
|chainwork|String (HEX)|Total number of hashes that are expected to have been necessary to produce the current chain|
|confirmations|Integer|Number of confirmations|
|previousblockhash|String (HEX)|256-bit hash of the previous block header|
|nextblockhash|String (HEX)|256-bit hash of the next block header|
|reward|String|Reward received|
|isMainChain|Boolean|Is the block part of the main chain|
|poolInfo|[PoolObject](#schemepoolobject)|Information about the pool on which the block was mined|

<a id="divider"></a>

> Example

```json
{
    "hash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
    "size": 8713,
    "height": 318135,
    "version": 2,
    "merkleroot": "2b83ee78f96048372661500f679658222e96771617a94ff5e4479c734a7ffb6f",
    "tx": [
        "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
        "8ac4006d584b3a5302811b454f04a965d617520d9edcd02f5fc5d5c2d181766d",
        "503824bd04ca2afa611a0e8be7ac2e8b16cbc56bb36fad8ec5ea063f8d61da9e"
    ],
    "time": 1421145649,
    "nonce": 2972589696,
    "bits": "1d00ffff",
    "difficulty": 1,
    "chainwork": "000000000000000000000000000000000000000000000001a4b84048b5079d0e",
    "confirmations": 1022140,
    "previousblockhash": "000000001c98fa1d82c41d2a2999aaba845e94bf9cb64656c748dd98cf9d78d4",
    "nextblockhash": "00000000cf98de1b48bddea4a25f6379e192e306303138db67ee5a7e013eefd8",
    "reward": 25,
    "isMainChain": true,
    "poolInfo": {}
}
```

<h2 id="tocPoolObject">PoolObject</h2>

<a id="schemepoolobject"></a>

|Name|Type|Description|
|---|---|---|
|poolName|String|Name if the pool|
|url|String|Pool URL|

<a id="divider"></a>

> Example

```json
{
    "poolName":"AntMiner",
    "url":"https://bitmaintech.com/"
}
```

<h2 id="tocBlockHashObject">BlockHashObject</h2>

<a id="schemeblockhashobject"></a>

|Name|Type|Description|
|---|---|---|
|blockHash|String (HEX)|256-bit hash of the block|

<a id="divider"></a>

> Example

```json
{
    "blockHash":"000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e"
}
```

<h2 id="tocRawBlockObject">RawBlockObject</h2>

<a id="schemerawblockobject"></a>

|Name|Type|Description|
|---|---|---|
|rawblock|String (HEX)|Raw block data|

<a id="divider"></a>

> Example

```json
{
    "rawblock": "02000000d4789dcf98dd48c75646b69cbf945e84baaa99292a1dc4821dfa981c000000006ffb7f4a739c47e4f54fa9171677962e225896670f506126374860f978ee832b31f6b454ffff001d801e2eb11901000000010000000000000000000000000000000000000000000000000000000000000000ffffffff0e03b7da0402e004062f503253482fffffffff0116d2049500000000232103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac00000000010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000010000000461f8ca726a88eb29d0d9fe03a09ad0702d3ed480a5e40e3094dd1c500dc4dfd4010000006a4730440220167741f5716be304506ef07f9a8d328cf549c9e00f9e5d8fa3a20516175300fc02207020760c7892f13443b0047e6725a917c5619531e0ebc3099d05947600f5d29801210253f16bdd8af3675fb7250132786b552215ffb3d7f068e872858af2ed9391be63ffffffff6f718299e8b41e8fda478049e74de601e07c5b8c077a6e593cad4d84cf343604010000006a47304402203e7fcc5267ccc96dd67265257317fe0a75883da01d62cd2db85b425f84ad3a3c0220700ba8c749e1fe0d5a1ff9490c279658c53151377d1e1325fb25390a6ab2e68501210253f16bdd8af3675fb7250132786b552215ffb3d7f068e872858af2ed9391be63ffffffff132d9bb3a75ac7ab07d45d5b9c26b7cefce62a484c272f8484de268897f90c71020000006a47304402203fc6f7ba7a44d7c97c58d7c1d1739b371f8f01b2dcf471c95be418cec0c8d3c4022046b7b97bb9fb51eebd0ecd0a33ebeee8fe9f795c95cf6b2cbeb065422a6c1a0401210253f16bdd8af3675fb7250132786b552215ffb3d7f068e872858af2ed9391be63ffffffff8a2043c8b1104e956ae16345afed89952498cda54dc8428a4d9bc221f1bb5c87010000008b483045022100f16e5e418263a029a1f547d5554edb5579386725fdc0a971626d1dd1dd8fa28102203296b9dba14d58313da03445a41ffca189d553fc36e3f4bef27a627f73b87e880141048dcb436c4c027e8a5826bdf3c8b6cb326abe66a2d34a18aa473442d8c535f902da45df071964fc8304658b20f9dd1ed241dc48578bf775624a9bd8c52b92c389ffffffff04571e7c00000000001976a914bf30968d077da70f0c7b139648f8a61e05cb699c88ac9105cb00000000001976a91434c31be013182cfa8c461b8a8d5ee753b928804488ac2877ad00000000001976a9143ff11c66327a1dfcb14644b4b341b2e08a9a0a1188acf092aa8d000000001976a9145af0fe772e1600100b2000f8279f78ce66b7e1d588ac0000000001000000015e6bf4b42fc51cbb533cba8a01bccecf198591f85eddcf2a8ecf3b2e7c2e532d010000008b483045022100f22cbcbeec5314fd1c6ae6ef1181a97a7c577ad2b066a5b1106e66c738bd40eb0220451698bf067e5cee483b60a3dbf86ef90dd04dd98a90caeb05f2e012da2336a90141040cfa3dfb357bdff37c8748c7771e173453da5d7caa32972ab2f5c888fff5bbaeb5fc812b473bf808206930fade81ef4e373e60039886b51022ce68902d96ef70ffffffff02a0860100000000001976a9143c22bd4e0865255c6ba0c032d5290625a85005d388ac88bea228000000001976a91461b469ada61f37c620010912a9d5d56646015f1688ac00000000010000000126ad7195653290f8222286450892a5035fd0ae75ec933fb7a78d998f6f6ac4e401000000fdff00004830450220233447743ca4905bb311811d8155be6a571437029808c66238a7416d8066a65d022100ba3023c9ff204b9581c2ba05de4f431adb9bf35e80b2e0bbd15e23d563bfeb4201493046022100a58fda101e11985a8814145e46f1aa5c0d01c9c2d291a7700625e3ef7ca83e9b022100c9ed62faa0dda26fdf9de23a0297b433f9a65e75571493a931c9bdd8f8486444014c69522102ea7545ef321d04186a2cd79e3af4a37b3f2ba48b5fc329ec25d3a2bebefc63b92103d45b9028fe98ae1e80a28b3ef076dc1c5068df7776bb047c4f30774ac09cfffc21038df59433fd09667bc7d2d8d6749fedf7850ce245ca256d06b4bd3b07e0fea1b653aeffffffff02a08601000000000017a9147b3b04e404fcb8bb0ad322cc6c8e490f3c4a704c8760ea00000000000017a914d1bc76ead855086c10a26b2580063561dddee03d87000000000100000001247fc12b477549a4d079341b1c41a95fd8aaf0402ba2f6730ff36a3d98237cff01000000fd660100473044022077ca5f2ace6c4987baa225ccfbab254161b6b4ebb71ddf5c67b9f9e7d9b55fc502206409f54d0b9a8ebe9726688361dc654315d46385d200c3f5ffb89450bf0c3a0c01473044022010b69f92d3cef7997d6445b14ed24d9d80a7b7be92269df9b8ac9c92684b4b6f02204ab89c198c5078bb2c4dffcf74f0328c207022243f993a53339de00cb8455bf501473044022062405159b1c273a925ffd84ce25d848325105fb2d0ae6f763fe62f1affa2c8840220748dfef56b1ea6616f8c32b2a48f84251ea63f1d750ea98039fdc34b41f981c9014c8b532102753f9d81917d569b978918885f7b4b9d06a8b069aa36a18dc886e25fa13641152103753ffaf07052cf55794c245fb0d0b59f4416e7226efa9381cc4040399aa7664b2103892d30dd36afcc4588cd3dd332fa6ab806a6992c6fd7d300527f12926e0a6c502103ad73da5d2d9ee36878bdde7803766459f083e9494438c07e7f9b340c1b0511ee54aeffffffff022f7500000000000017a9147d199f8c0991a1b196d36dfc1c3006ef65df9bc087b75003000000000017a9146ffdbdb8cad0bf1db77a53b2468eb764533b927d87000000000100000001906190907a7aa7169c5adb98bfa6b6a29150f957f5b91d82db26d39af0ce27c201000000fd680100483045022100e42a917da891fe2abddd91ff000143b9431158d92af88fa96d8451e8976e100102204b94217335c8e090f0bbd25d4ba1a13759a8342678ac9b87e1bfee2f824baffb01483045022100e8850433ffe8e8d359782458b3bfd83540e7cb9bf029ec35590fd68c1a0f0bb902206b46758a144906c18a77332cd06509b81ee7c00979e06060d393a8c742fcbe690147304402203c9054dc16d275ec0892e988647df0961729265ee881b5c143f4b485191addb7022047550a925fdc68a824a99d8890136275e257960cf4f3038f73333cba372046ce014c8b532102753f9d81917d569b978918885f7b4b9d06a8b069aa36a18dc886e25fa13641152103753ffaf07052cf55794c245fb0d0b59f4416e7226efa9381cc4040399aa7664b2103892d30dd36afcc4588cd3dd332fa6ab806a6992c6fd7d300527f12926e0a6c502103ad73da5d2d9ee36878bdde7803766459f083e9494438c07e7f9b340c1b0511ee54aeffffffff022f7500000000000017a9147d199f8c0991a1b196d36dfc1c3006ef65df9bc08778b402000000000017a9146ffdbdb8cad0bf1db77a53b2468eb764533b927d870000000001000000039eda618d3f06eac58ead6fb36bc5cb168b2eace78b0e1a61fa2aca04bd243850000000006a47304402202896e7c4b538528315a67cc44c799f6ff79ac11c172aff5ea19da3ef044bad2c022055bdb1f10b99e9d4a2d5f984fa29fc3bb4fc7471de8aaed8b74f13e9801f775201210202913453438a13379fde97511771df0a55621e0e0efa7e336fecf97dcb1d0cc4ffffffff6f718299e8b41e8fda478049e74de601e07c5b8c077a6e593cad4d84cf343604000000006a473044022076e161f82188bbb29074cf010a29134603d193713cfd37fc58ce094a0af81bab022064b03ba7cdb46c23b2d3f99bc2d95365ee905106a56f6c5307a7f3893eeadc0701210202913453438a13379fde97511771df0a55621e0e0efa7e336fecf97dcb1d0cc4ffffffff27c97305b6866a8acbcf2ad0c89361eacbe9717f30d3a47dd71fcca3c5a8e032020000006b483045022100f350b4b686db9df7c526d981484d0e3abcc813f71afc75946aab2b3eed6cf132022033a3561a8b0cd899658e3214cd116a0039dcc0edbc07e824ec5a826c4e37ceeb01210387a7f58f7bdb43dcf2f4a6fcd68234e85761fc3df225ab3bde2aebf2581333c8ffffffff0315fb6e00000000001976a9143f90d6a172287d2716fac1179ccd7dabeea7841b88ac59e5ff04000000001976a914bf30968d077da70f0c7b139648f8a61e05cb699c88acf9b1f201000000001976a9144e2a84f0f0d13d1b06c00b9ca37f6ade6bfe539d88ac00000000010000000361f8ca726a88eb29d0d9fe03a09ad0702d3ed480a5e40e3094dd1c500dc4dfd4020000006b483045022100ff16e2fafed10cf4eda0b45733f23b78aa588aded5d3ec165aa947ca0d4b65e8022032a6e4083ed663e5b7f581672c21a7ebc072aa5345ba7cf46b839c55d97417510121039c36a297f7dfc1411830f7882fc66e45971f07dc5a2fb9e565598ff17b083a76ffffffff9eda618d3f06eac58ead6fb36bc5cb168b2eace78b0e1a61fa2aca04bd243850020000006b4830450221009095b36fa5c8e36b407ce56f5085e7d6e630f0156feaca7daf970d9cc9087f2702207d2815306bd2a72df1344a5cdeef3b0e3baaf37f4527e8cdb01b0f9721f679b00121039c36a297f7dfc1411830f7882fc66e45971f07dc5a2fb9e565598ff17b083a76ffffffff7bcb6bd0b86ec8b195d04ab8da90d88007555160169a70591a34badb084c6a38010000006a4730440220795480a734feabe03a856d256700657954c1bfca94b817747cfcb86cb806571d022036a3c5243bfca8a4fe3fbc2f8057abf3d08bf787c78a2e1bb9199a06760abb9e01210202913453438a13379fde97511771df0a55621e0e0efa7e336fecf97dcb1d0cc4ffffffff030e549100000000001976a9143f90d6a172287d2716fac1179ccd7dabeea7841b88ace9408d02000000001976a914bf30968d077da70f0c7b139648f8a61e05cb699c88accb721f06000000001976a9143ff11c66327a1dfcb14644b4b341b2e08a9a0a1188ac00000000010000000361f8ca726a88eb29d0d9fe03a09ad0702d3ed480a5e40e3094dd1c500dc4dfd4000000006b48304502210097ac9e471fae9b0b0713d6de614557bcc2ece715305e4feabe606d0089a78e5a022047fa460af36b0b005063f052164b2254bec8485dc27da73f3e2e824dd6c0d8a001210353c62ffca6dbb66c84d363d58e2c4f1583dbcde1a246359dab46ebf1b0e8b1b5ffffffffcc8cf9fed789564aa50fded1afb0292a54a2b82dc96f9e76766076c20c308fe9020000006b483045022100f7958364f1ccbb34cd03793f4eb190b871a604b93a263f89ab932587a459bcc302206a9cb26aa814f3af4300819e796724bfca2818908ad268174e1bf4c7a7ee77350121039c36a297f7dfc1411830f7882fc66e45971f07dc5a2fb9e565598ff17b083a76ffffffff9eda618d3f06eac58ead6fb36bc5cb168b2eace78b0e1a61fa2aca04bd243850010000006a4730440220718d9b87ab4f99007a78443ae25038dc56def7c8287421f1951c3942f6efe30502202ad7d838bf1fcfddf5b88ca3b4b2723d35f3f3ed731ef4edc6e65f3e22485cff01210353c62ffca6dbb66c84d363d58e2c4f1583dbcde1a246359dab46ebf1b0e8b1b5ffffffff033f09b100000000001976a9143f90d6a172287d2716fac1179ccd7dabeea7841b88acb085af06000000001976a91434c31be013182cfa8c461b8a8d5ee753b928804488ac3ef41b03000000001976a9143ff11c66327a1dfcb14644b4b341b2e08a9a0a1188ac000000000100000002a02d4abac9733dca59064eba3399917b20ba55c49ce19159c6e002381584de55010000006b483045022100e81f0489e72b585879ab5de6f857a59b50f11003b99f26b29567678e4c3df15f02205720616fe89fb57ecbc24730e79c59b2bd8b1c01842206c65efc4888bc8f428b01210353c62ffca6dbb66c84d363d58e2c4f1583dbcde1a246359dab46ebf1b0e8b1b5ffffffff7bcb6bd0b86ec8b195d04ab8da90d88007555160169a70591a34badb084c6a38020000006b483045022100c280a87a23350ece31854957f4901339004e49bb175ef4827393604d111c102a02203a6fba2c22cbc01948f69fc17153a126dd0dc086d2d5e99990799c12dbf7a4c301210387a7f58f7bdb43dcf2f4a6fcd68234e85761fc3df225ab3bde2aebf2581333c8ffffffff03fcd6e103000000001976a91434c31be013182cfa8c461b8a8d5ee753b928804488ac8d36e303000000001976a9144e2a84f0f0d13d1b06c00b9ca37f6ade6bfe539d88ac1003dd00000000001976a914971a09a99a4a5cdcf609ca303dca76e799e7fc7688ac000000000100000004855f4aeb2994eee277f396b8ea4a1d26a8f6a05880949f6a3452984b5850cd11000000006a47304402202ed66d6a248abab28735fc0e02c1a067101743ff4ffde43c13930d2c72e52cf40220677e012b4f6b8162d6b3b69371c7094c12a611a8ded00735164c75784702ca43012103487d1d18e898053ed276acaf81efbf8ad697563df0d3298cfd473d8b534f4b26ffffffff9eda618d3f06eac58ead6fb36bc5cb168b2eace78b0e1a61fa2aca04bd243850030000008b483045022100e8ad8a136ff9fb06e34e084bf330bf8dc9961946c23a913b9991c6e2fa748c790220229b9630f9fddb7e4ce8c4b5253690a402f6b4167d71c52166a8809446ef6a510141048dcb436c4c027e8a5826bdf3c8b6cb326abe66a2d34a18aa473442d8c535f902da45df071964fc8304658b20f9dd1ed241dc48578bf775624a9bd8c52b92c389ffffffff27c97305b6866a8acbcf2ad0c89361eacbe9717f30d3a47dd71fcca3c5a8e032000000006a47304402204c7caf979e88a9c83e1050dce3307971879a17f4f1edfdedf163627032e9c1d30220098a936946306002f98109c6e04ad05934450c11f79f457a4a4361bdbaafeaf8012103487d1d18e898053ed276acaf81efbf8ad697563df0d3298cfd473d8b534f4b26ffffffffa77cc051c94432376fe0b30ff0b9ba71b8f39c8a5540742b866532cad0bf3ede000000006b483045022100bf21a457bce6b98ed3d4d2bc23da340cebd5aed4df59dc09e66178cdcc6d718402206360905e1e8887a7a3f27415d958572d8f7ec52b26dbe31cba35cea2390e97b8012103487d1d18e898053ed276acaf81efbf8ad697563df0d3298cfd473d8b534f4b26ffffffff0211103c02000000001976a914f4f065395c82c6f28d3c73cef113d6da0f90d82a88ac80f2ab8d000000001976a9145af0fe772e1600100b2000f8279f78ce66b7e1d588ac00000000010000000395856ab90307755e0e201840dfaae56e22d8bdedbbd9bea17f27247ed0970731000000006a473044022035960414798d2b29532bef2a03b0a7a47875a5b049b85cf60be8806db91e47ee02204634859e7a2ddaa645a5614775b24de4eb28147843f1044196ee8e4f41de6f580121030a3c4a2c8acfde0b4187c47dd69d9b0e6f668ae995856a195b2bc145de7a241effffffff2653b74223ad8de3f3cba38ebfff1a9a6748934d84f49e686cd74de1febeba48010000006a4730440220761b31a3b5f5099682cdbcdeb8761e687596e478e77ed7f33e0dab46b5e3188f02206b55cd535ddb7034ea0230db92b3932cf130ac5e6b99e011ecd0bcfc165e9eb201210387a7f58f7bdb43dcf2f4a6fcd68234e85761fc3df225ab3bde2aebf2581333c8ffffffffa77cc051c94432376fe0b30ff0b9ba71b8f39c8a5540742b866532cad0bf3ede010000006a47304402200e298b608b28d6e74174607bc836862eb8f44c83a9de2ea7259242e22e754be102203f9b5ff20c8454e7d1e5774d3f4e8131bf5f030bb21a8a44ee4676da039233eb0121030a3c4a2c8acfde0b4187c47dd69d9b0e6f668ae995856a195b2bc145de7a241effffffff033ca1db05000000001976a914f4f065395c82c6f28d3c73cef113d6da0f90d82a88acfa82c002000000001976a9144e2a84f0f0d13d1b06c00b9ca37f6ade6bfe539d88ac09ba9c00000000001976a914971a09a99a4a5cdcf609ca303dca76e799e7fc7688ac000000000100000002bcc202e5a24fa158cb527a36da8f5e4efd167c1123a45af375ef29c5042f6e7c000000006b4830450221009e9a8e00f20479a3e0a988d1c1b59ea14784bc6e73a901376f954867567c194f022005769d3d3e427a1e1a1b6252cb6f6d6936f86fcfa32cc33ead281ba784db854d0121030a3c4a2c8acfde0b4187c47dd69d9b0e6f668ae995856a195b2bc145de7a241effffffffcc8cf9fed789564aa50fded1afb0292a54a2b82dc96f9e76766076c20c308fe9010000006b483045022100a6d87766e0cbfdf0badf55e8cf0c3345dd0334ab2cb80f15165c18576820cbc60220525e5300d59204ac83946a0d5c977dd44ea9ded330b2c77a4b278c3f939c365b01210202913453438a13379fde97511771df0a55621e0e0efa7e336fecf97dcb1d0cc4ffffffff033668c903000000001976a914bf30968d077da70f0c7b139648f8a61e05cb699c88aca508c803000000001976a914f4f065395c82c6f28d3c73cef113d6da0f90d82a88ac3a4ad700000000001976a914971a09a99a4a5cdcf609ca303dca76e799e7fc7688ac000000000100000001850a715b08ab33a980490a47d51eb8b2378323a9f2384a3168acab2905a89c20000000006a47304402202c676281eb5844649731db1d03439f377f32f9c09b2b2a6ce5dbc0e47c579e4702205fe57673f9c842e5a20f501cd7c0a3ba350d1e966880f9900c9a1ccd3430d1f0012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0198d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac00000000010000000185a692ca91206cba789b9abbe5d6cadc64af72f1f1b90a885e454c363ea56abf000000006a47304402207ee30301e67509658bd1f7726b236e6f650bdacb1e58dc16d269e36958a5521e022044c9737f6199645d38f1ca408f5b310b36c5dbb7d30f1f408622e167cf45c72f012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff018ed72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac0000000001000000017c352db1f54c8e1acf498ff60a134e5daf8dc74541cc9a77d64513d1b3b1d26e000000006b483045022100eb98e7518e6919290bbc9e83b966786094ffe821580f4c38ffbfe2469040d81a022062085e9926923eabe9be65f63d9ccd8f727caef32bf8b90ba3a95fd13500a1ab012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0184d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac000000000100000001559d2e24b5b22496e6b45cde49b859da1ca991023eeeec9991a17ce9000867f0000000006b483045022100f7de1a07ec6db58e589555827cf25e79c85dc634ed9760157755d5966e6543d102204b2dd188cbbd71565791d1b6e7a00fa19f4aad1f1648dfb5d0c8ae57ac046732012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff017ad72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac000000000100000001e3f0be4312852db0b1047454aae31ade9f230b104c4b0811543ee73759ab56d5000000006a47304402203c90ad5689dcbdf750558a5c983ca83a0ddf645135051fc82100e6e52b36c29c0220037972366f5740f1b30e3c0ddc96ea69dbd36a6236cab867ab068b42282a1e6c012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0170d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac000000000100000001a340d8ce9ba4e80edcd0d66661491d712cd95c68f34d3bd09b8c93d9a6ccca67000000006a47304402201eec765987b8ce56414f39dc6ef41402400fcdd47af1dc3aac15d2970b44def2022020fa2e38f4b757f82048024465a59dab432bc488c4a11211f232e1d273eb0cfc012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0166d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac0000000001000000019ec9d0a5d49f928fa2373a83bd081e67493841b68b2ef334c97525f8acc92a72000000006b483045022100b9cf1dee09ea57da66e29a3d17a8123c43205f8ea16e047e3af14e96378c91c6022041d70767a97bdbddcb986c582b31650220949f37319c09717feb587c37f1d25b012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff015cd72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac0000000001000000015a6b5aa0f1d1ba73f4c26b6fa90e40700f9266302e38b2faf2d7aae30e1e798a000000006a47304402204caf5e53a686b063de81d36fb32edd5d17beb553ce70956d0fc420c557359b85022005042d5b0e01d9db0e0cef20f147d485ac4acc30bfda9e00451f0dc1b47e77b8012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0152d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac0000000001000000015a5debc66642e3c660c8036b7f83bd4256dafc1b60593fb2c7cbfb9b1a722370000000006b483045022100e76b03268f8449653028b3bb9958a2145465b07536ff17c4faa7feb2c98c9d6d0220488b7d94ea1fda3b34ada8ba17925ce1bfd6aa88bd87e9ac789400fd29a5e87a012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0148d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac0000000001000000015d1bd886c44dd6db0b5b2d401572a08264dfaa1675cb6ce396ecea67835b2afd000000006b483045022100a81f92fc3c1fb8e1f1968c5a6227347396993a0d1c17517bcc54dede4900d7ee02206c043b991cd3c6433475c20f9c239f44c2730d568e3b600662fbce1ac6f8e73e012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff013ed72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac000000000100000001df1d48daf53eee25178a0abff7fd64afb322a07143721f183a21ec7ea2c22bca000000006b483045022100fee0b6f7540a60b85e0e0b3c34c2badcdf74d375e2c8c0dd902fbc7ac5a6f87f02204bed33a8efb49042d4322c97627042f618c4fa76aea7c8f661969d1078fdbfaf012102fee381c90149e22ae182156c16316c24fe680a0e617646c3d58531112ac82e29ffffffff0134d72f01000000001976a914b96b816f378babb1fe585b7be7a2cd16eb99b3e488ac00000000"
}
```

<h2 id="tocBlocksPaginatedObject">BlocksPaginatedObject</h2>

<a id="schemeblockspaginatedobject"></a>

|Name|Type|Description|
|---|---|---|
|block|Array of [BlockPagObject](#schemeblockpagobject)|Array of BlockPagObjects|
|length|Integer|Number of blocks|
|pagination|[PaginationObject](#schemepagintionobject)|Pagination metadata|

<a id="divider"></a>

> Example

```json
{
    "blocks": [
        {
            "height": 1287218,
            "size": 31890,
            "hash": "00000000a9ea5cfdbb3f76629fc316be3728e27bd5118533c0b23877dfe469ed",
            "time": 1520120863,
            "txlength": 117,
            "poolInfo": {}
        },
        {
            "height": 1287217,
            "size": 27990,
            "hash": "000000006452408143efa7561706483fc132c88f935f27321d826d9a6445a77f",
            "time": 1520119662,
            "txlength": 94,
            "poolInfo": {}
        },
        {
            "height": 1287216,
            "size": 234,
            "hash": "00000000afae877f449a09ae5e560a56055f4bc4ac32d002b1bd07b228c23f3c",
            "time": 1520118461,
            "txlength": 1,
            "poolInfo": {}
        }
    ],
    "length": 3,
    "pagination": {
        "next": "2018-03-04",
        "prev": "2018-03-02",
        "currentTs": 1520121599,
        "current": "2018-03-03",
        "isToday": false,
        "more": true,
        "moreTs": 1520121600
    }
}
```

<h2 id="tocBlocksPagObject">BlocksPagObject</h2>

<a id="schemeblockpagobject"></a>

|Name|Type|Description|
|---|---|---|
|height|Integer|Block height in the chain|
|size|Integer|Size of the block|
|hash|String (HEX)|Hash of the block|
|time|Integer|Timestamp as seconds since 1970-01-01T00:00 UTC|
|txlength|Integer|Number of transactions in the block|
|poolInfo|[PoolObject](#schemepoolobject)|Information about the pool on which the block was mined|

<a id="divider"></a>

> Example

```json
{
    "height":847606,
    "size":11315,
    "hash":"0000000000000011c33a17cffcee559bf18b38f479462c1426cabd71ce57d944",
    "time":1522799887,
    "txlength":21,
    "poolInfo":
    {
        "poolName":"AntMiner",
        "url":"https://bitmaintech.com/"
    }
}
```

<h2 id="tocPaginationObject">PaginationObject</h2>

<a id="schemepagintionobject"></a>

|Name|Type|Description|
|---|---|---|
|next|String|Next date in format YYYY-MM-DD|
|prev|String|Previous date in format YYYY-MM-DD|
|currentTs|Integer|Current timestamp since epoch|
|current|String|Current date in format YYYY-MM-DD|
|isToday|Boolean|Is current day from the request today|
|more|Boolean|Is there more than specified number of resources|
|moreTs|Integer|Timestamp since epoch|

<a id="divider"></a>

> Example

```json
{
      "next":"2018-04-04",
      "prev":"2018-04-02",
      "currentTs":1522799999,
      "current":"2018-04-03",
      "isToday":false,
      "more":true,
      "moreTs":1522800000
}
```

<h2 id="tocTransactionObject">TransactionObject</h2>

<a id="schemetransactionobject"></a>

|Name|Type|Description|
|---|---|---|
|txid|String (HEX)|Hash of the transaction|
|version|Integer|Version|
|locktime|Integer|Timestamp since epoch - time at which a particular transaction can be added to the blockchain.|
|vin|Array of [TxIN](#schemetxinobject)|Array of TxIN Objects - input transactions|
|vout|Array of [TxOUT](#schemetxoutobject)|Array of TxOUT Objects - output transactions|
|blockhash|String (HEX)|Hash of the block containing tx|
|blockheight|Integer|Height of the block containing the transaction|
|confirmations|Integer|Number of confirmations|
|time|Integer|Timestamp of the transaction since epoch|
|blocktime|Integer|Block timestamp since epoch|
|valueOut|Float|Output Value in BTC|
|size|Integer|Size of the tx in bytes|
|valueIn|Float|Input Value in BTC|
|fees|Float|Network fee for the transaction|
|isCoinBase|Boolean|Is the transaction general one created by miner/first in a block.|

<a id="divider"></a>

> Example

```json
{
    "txid": "8ac4006d584b3a5302811b454f04a965d617520d9edcd02f5fc5d5c2d181766d",
    "version": 1,
    "locktime": 0,
    "vin": [
        {
            "txid": "bc20074793ffabb7ef99979ab40b2a347cd360900ee88ec9546bce2c692dfa76",
            "vout": 1,
            "sequence": 4294967295,
            "n": 0,
            "scriptSig": {
                "hex": "00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae",
                "asm": "0 3046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f[ALL] 304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b[ALL] 522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae"
            },
            "addr": "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX",
            "valueSat": 4657658000,
            "value": 46.57658,
            "doubleSpentTxID": null
        }
    ],
    "vout": [
        {
            "value": "0.01000000",
            "n": 0,
            "scriptPubKey": {
                "hex": "a914834be63f7d9d48ea1797cbe84282cdf4617246fc87",
                "asm": "OP_HASH160 834be63f7d9d48ea1797cbe84282cdf4617246fc OP_EQUAL",
                "addresses": [
                    "2N5DTRzmxKiJC3uuo39kqXTxhuSJQpoB3y2"
                ],
                "type": "scripthash"
            },
            "spentTxId": null,
            "spentIndex": null,
            "spentHeight": null
        },
        {
            "value": "46.56657000",
            "n": 1,
            "scriptPubKey": {
                "hex": "a9148ce5408cfeaddb7ccb2545ded41ef4781094548487",
                "asm": "OP_HASH160 8ce5408cfeaddb7ccb2545ded41ef47810945484 OP_EQUAL",
                "addresses": [
                    "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX"
                ],
                "type": "scripthash"
            },
            "spentTxId": "77f39aa8c490783c3615f821a174a53abacb703e4954f5bbab1b4b5613ca1533",
            "spentIndex": 0,
            "spentHeight": 318177
        }
    ],
    "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
    "blockheight": 318135,
    "confirmations": 1022347,
    "time": 1421145649,
    "blocktime": 1421145649,
    "valueOut": 46.57657,
    "size": 334,
    "valueIn": 46.57658,
    "fees": 0.00001,
    "isCoinBase": true
}
```

<h2 id="tocTxIN">TxIN</h2>

<a id="schemetxinobject"></a>

|Name|Type|Description|
|---|---|---|
|txid|String (HEX)|Hash of the transaction|
|vout|Integer|The index of the output being spent within the transaction. Zero based.|
|sequence|Integer|Legacy 4-byte sequence number. A number intended to allow unconfirmed time-locked transactions to be updated before being finalized;|
|n|Integer ||
|scriptSig|[ScriptSig Object](#schemescriptsigobject)|Signature script - a script included in the input which complies with conditions set by ScriptPubKey in order to spend funds.|
|addr|String (HEX) |Address associated with the output of the previous transaction|
|valueSat|Integer|Value in satoshis|
|value|Float|Value in BTC|
|doubleSpentTxID|String (HEX)|ID of the double spend tx; Double spends are not currently tracked|

<a id="divider"></a>

> Example

```json
{
    "txid":"f2d8b042224c57740e5e867e1b317ed450f85fb2bb69d77bafcf975ca95efbc0",
    "vout":1,
    "sequence":4294967295,
    "n":0,
    "scriptSig":
    {
        "hex":"483045022100f52b7a776e0cd7c398fc794d46119a2b2a9273b88d9c044f79e694b5d1e97880022072eb161ca507eb5af20c63024404c44b0e691c45df6acdc4e2f7bf8229c84d4d012102dfc9f8086e802047a5cefb745c3191c84f57bed47816f07a7bbe41ab134e228a",
        "asm":"3045022100f52b7a776e0cd7c398fc794d46119a2b2a9273b88d9c044f79e694b5d1e97880022072eb161ca507eb5af20c63024404c44b0e691c45df6acdc4e2f7bf8229c84d4d[ALL] 02dfc9f8086e802047a5cefb745c3191c84f57bed47816f07a7bbe41ab134e228a"
    },
    "addr":"Xoj4Qqx69FU3HbEidASNctRb7JpHDFG9s1",
    "valueSat":48225393,
    "value":0.48225393,
    "doubleSpentTxID":null
}
```

<h2 id="tocTxOUT">TxOUT</h2>

<a id="schemetxoutobject"></a>

|Name|Type|Description|
|---|---|---|
|value|Float|Value in BTC|
|n|Integer|The index of the output being spent within the transaction. Zero based.|
|scriptPubKey|[ScriptPubKey Object](#shemescriptpubkeyobject)|A script included in outputs which sets the conditions that must be fulfilled for funds to be spent.|
|spentTxId|String (HEX) |Id of the transaction spending funds|
|spentIndex|Integer|The main purpose is to efficiently determine the address and amount of an input's previous output. The second purpose is to be able to determine which input spent an output.|
|spentHeight|Integer|Height of the block which includes the transaction|

<a id="divider"></a>

> Example

```json
{
    "value":"4.58822623",
    "n":0,
    "scriptPubKey":
    {
        "hex":"76a914f9a86dca25067c5bf4a784aebd27080f3ec06f4c88ac",
        "asm":"OP_DUP OP_HASH160 f9a86dca25067c5bf4a784aebd27080f3ec06f4c OP_EQUALVERIFY OP_CHECKSIG",
        "addresses":
        [
            "XySurfMBRDFFXhwWnLRYk6LPzESyamG9c4"
        ],
        "type":"pubkeyhash"
    },
    "spentTxId":"026cd76659232a3440028f1b706756546dfce29875a443a38db91b68d698e958",
    "spentIndex":0,
    "spentHeight":803642
}
```

<h2 id="tocScriptSigObject">ScriptSig</h2>

<a id="schemescriptsigobject"></a>

|Name|Type|Description|
|---|---|---|
|hex|String (HEX)|Serialised form of the script in hex encoding.|
|asm|String|De-serialised form of the script, with well-known tokens parsed as script tokens.|

<a id="divider"></a>

> Example

```json
{
    "hex":"483045022100f52b7a776e0cd7c398fc794d46119a2b2a9273b88d9c044f79e694b5d1e97880022072eb161ca507eb5af20c63024404c44b0e691c45df6acdc4e2f7bf8229c84d4d012102dfc9f8086e802047a5cefb745c3191c84f57bed47816f07a7bbe41ab134e228a",
    "asm":"3045022100f52b7a776e0cd7c398fc794d46119a2b2a9273b88d9c044f79e694b5d1e97880022072eb161ca507eb5af20c63024404c44b0e691c45df6acdc4e2f7bf8229c84d4d[ALL] 02dfc9f8086e802047a5cefb745c3191c84f57bed47816f07a7bbe41ab134e228a"
}
```

<h2 id="tocScriptPubKeyObject">ScriptPubKey</h2>

<a id="schemescriptpubkeyobject"></a>

|Name|Type|Description|
|---|---|---|
|hex|String (HEX)|Serialised form of the script in hex encoding.|
|asm|String|De-serialised form of the script, with well-known tokens parsed as script tokens.|
|address|Array of Strings|Public addresses|
|type|String|Type of the script|

<a id="divider"></a>

> Example

```json
{
    "hex":"76a914f9a86dca25067c5bf4a784aebd27080f3ec06f4c88ac",
    "asm":"OP_DUP OP_HASH160 f9a86dca25067c5bf4a784aebd27080f3ec06f4c OP_EQUALVERIFY OP_CHECKSIG",
    "addresses":
    [
        "XySurfMBRDFFXhwWnLRYk6LPzESyamG9c4"
    ],
    "type":"pubkeyhash"
}
```

<h2 id="tocTxBlockObject">TxBlockObject</h2>

<a id="schemetxblockobject"></a>

|Name|Type|Description|
|---|---|---|
|pagesTotal|Integer|Total number of pages.|
|txs|Array of [TransactionObject] (#schemetransactionobject)|Array of Transactions in the block|


<a id="divider"></a>

> Example

```json
{
    "pagesTotal": 1,
    "txs": [
        {
            "txid": "8ac4006d584b3a5302811b454f04a965d617520d9edcd02f5fc5d5c2d181766d",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "txid": "bc20074793ffabb7ef99979ab40b2a347cd360900ee88ec9546bce2c692dfa76",
                    "vout": 1,
                    "sequence": 4294967295,
                    "n": 0,
                    "scriptSig": {
                        "hex": "00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae",
                        "asm": "0 3046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f[ALL] 304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b[ALL] 522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae"
                    },
                    "addr": "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX",
                    "valueSat": 4657658000,
                    "value": 46.57658,
                    "doubleSpentTxID": null
                }
            ],
            "vout": [
                {
                    "value": "0.01000000",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "a914834be63f7d9d48ea1797cbe84282cdf4617246fc87",
                        "asm": "OP_HASH160 834be63f7d9d48ea1797cbe84282cdf4617246fc OP_EQUAL",
                        "addresses": [
                            "2N5DTRzmxKiJC3uuo39kqXTxhuSJQpoB3y2"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                },
                {
                    "value": "46.56657000",
                    "n": 1,
                    "scriptPubKey": {
                        "hex": "a9148ce5408cfeaddb7ccb2545ded41ef4781094548487",
                        "asm": "OP_HASH160 8ce5408cfeaddb7ccb2545ded41ef47810945484 OP_EQUAL",
                        "addresses": [
                            "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": "77f39aa8c490783c3615f821a174a53abacb703e4954f5bbab1b4b5613ca1533",
                    "spentIndex": 0,
                    "spentHeight": 318177
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1022347,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
    ]
}
?>
```

<h2 id="tocTxAddressesObject">TxAddressesObject</h2>

<a id="schemetxaddressesobject"></a>

|Name|Type|Description|
|---|---|---|
|totalItems|Integer|Total number of transactions.|
|from|Integer|Start number (zero based index)|
|to|Integer|End number (zero based index)|
|items|Array of [TransactionObject] (#schemetransactionobject)|Array of Transactions|


<a id="divider"></a>

> Example

```json
{
    "totalItems": 282635,
    "from": 0,
    "to": 10,
    "items": [
        {
            "txid": "5d1cd03253b2aa892266abae5a4037f3c6aa1b728c406effee36c14c85cb93d7",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "txid": "ff2726b47ba99a14868e864214162e439acd2f8e039b6c56d1630f8dcaacfa9f",
                    "vout": 1,
                    "sequence": 4294967295,
                    "n": 0,
                    "scriptSig": {
                        "hex": "0047304402206761a58a75653de4d1d399cb01d06860d112b4de3e6bc47e5de854787fe83e3d02206f63b7561f1957196654891a34a101b2343532b7843b15ac83f8b7b48d6e576401473044022036da3d835f200dbcceb8371c3526606e8d91e3f6a23952c33516336ea9891d1d022051075ab60ccf9f4ade68264aa7b67e73cc12da5c5f167c09249e618f4e70c4280147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae",
                        "asm": "0 304402206761a58a75653de4d1d399cb01d06860d112b4de3e6bc47e5de854787fe83e3d02206f63b7561f1957196654891a34a101b2343532b7843b15ac83f8b7b48d6e5764[ALL] 3044022036da3d835f200dbcceb8371c3526606e8d91e3f6a23952c33516336ea9891d1d022051075ab60ccf9f4ade68264aa7b67e73cc12da5c5f167c09249e618f4e70c428[ALL] 522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae"
                    },
                    "addr": "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX",
                    "valueSat": 8547597,
                    "value": 0.08547597,
                    "doubleSpentTxID": null
                },
                {
                    "txid": "93e078983809c4bb6d18bef5cb083a644570e40acd84ea13e7d065db791a0a29",
                    "vout": 2,
                    "sequence": 4294967295,
                    "n": 1,
                    "scriptSig": {
                        "hex": "004730440220791d4745c2d4d9b97d6686ccfb9a54a6540c26090b1ab9097371da21fa540ee40220184b0f6f603c30a8da0467b04833259a5e775f5e9f56146393e0ba7bd42d01a301483045022100c48ff054c023540e2936c779a1932f58e8f66811ab6b55b2a54450ccffb6ba780220786b06fd8a397eabd6fbe341e743fb675fc09b353b7c824ed241fa1553ef887f0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae",
                        "asm": "0 30440220791d4745c2d4d9b97d6686ccfb9a54a6540c26090b1ab9097371da21fa540ee40220184b0f6f603c30a8da0467b04833259a5e775f5e9f56146393e0ba7bd42d01a3[ALL] 3045022100c48ff054c023540e2936c779a1932f58e8f66811ab6b55b2a54450ccffb6ba780220786b06fd8a397eabd6fbe341e743fb675fc09b353b7c824ed241fa1553ef887f[ALL] 522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452ae"
                    },
                    "addr": "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX",
                    "valueSat": 2000000,
                    "value": 0.02,
                    "doubleSpentTxID": null
                }
            ],
            "vout": [
                {
                    "value": "0.10000000",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "a914d89fd55cb6017965a6ce6d35dff791e546fc549c87",
                        "asm": "OP_HASH160 d89fd55cb6017965a6ce6d35dff791e546fc549c OP_EQUAL",
                        "addresses": [
                            "2NCzdR9BPWM8wZjjEVR2TWQmh7Dgw3fzCpW"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                },
                {
                    "value": "0.00542107",
                    "n": 1,
                    "scriptPubKey": {
                        "hex": "a9148ce5408cfeaddb7ccb2545ded41ef4781094548487",
                        "asm": "OP_HASH160 8ce5408cfeaddb7ccb2545ded41ef47810945484 OP_EQUAL",
                        "addresses": [
                            "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                }
            ],
            "blockhash": "000000002ded9228318cd6b671eb23a4e042d72f68bd12f0dc4d25d7a1462dcb",
            "blockheight": 1289143,
            "confirmations": 53664,
            "time": 1521980665,
            "blocktime": 1521980665,
            "valueOut": 0.10542107,
            "size": 591,
            "valueIn": 0.10547597,
            "fees": 0.0000549
        },
        {
            "txid": "1542a956d526efb5eb72446fdba5103f0372c9c1f70cc3120067242660d1a4ff",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "txid": "93e078983809c4bb6d18bef5cb083a644570e40acd84ea13e7d065db791a0a29",
                    "vout": 0,
                    "sequence": 4294967295,
                    "n": 0,
                    "scriptSig": {
                        "hex": "4730440220388ce2c854e67b486dd668bb8c0570eac48121dafa178221cf5f005a6eca744c02207a0cf45a22fc4b1dd53f46cad62031493d63ad1d3442004a0fc4bb34eeb4a6000121023788c0f182e15a234009a8492bf1be3d2f3350fe16acda511a507d2741e3fe67",
                        "asm": "30440220388ce2c854e67b486dd668bb8c0570eac48121dafa178221cf5f005a6eca744c02207a0cf45a22fc4b1dd53f46cad62031493d63ad1d3442004a0fc4bb34eeb4a600[ALL] 023788c0f182e15a234009a8492bf1be3d2f3350fe16acda511a507d2741e3fe67"
                    },
                    "addr": "miDnFCqSr2uJB3Yoqi86Jo8q5xDjRm8V3Q",
                    "valueSat": 76471810,
                    "value": 0.7647181,
                    "doubleSpentTxID": null
                }
            ],
            "vout": [
                {
                    "value": "0.74368810",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "76a9141da8eadbba4e694ee4c3672cd8a552de360197cd88ac",
                        "asm": "OP_DUP OP_HASH160 1da8eadbba4e694ee4c3672cd8a552de360197cd OP_EQUALVERIFY OP_CHECKSIG",
                        "addresses": [
                            "miDnFCqSr2uJB3Yoqi86Jo8q5xDjRm8V3Q"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "6a96fcd900523784a5658cc2826500bff4fa9cee9aa318287b9eae8b1b1819e2",
                    "spentIndex": 0,
                    "spentHeight": 1289143
                },
                {
                    "value": "0.02000000",
                    "n": 1,
                    "scriptPubKey": {
                        "hex": "a914c8a1fd3a23528380f48ab0091e897966abef78e287",
                        "asm": "OP_HASH160 c8a1fd3a23528380f48ab0091e897966abef78e2 OP_EQUAL",
                        "addresses": [
                            "2NBY5BrXhnWESaLqxYvRWUZ8xzDF3aZqX7S"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                },
                {
                    "value": "0.00100000",
                    "n": 2,
                    "scriptPubKey": {
                        "hex": "a9148ce5408cfeaddb7ccb2545ded41ef4781094548487",
                        "asm": "OP_HASH160 8ce5408cfeaddb7ccb2545ded41ef47810945484 OP_EQUAL",
                        "addresses": [
                            "2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX"
                        ],
                        "type": "scripthash"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                },
                {
                    "value": "0.00000000",
                    "n": 3,
                    "scriptPubKey": {
                        "hex": "6a216b65657020746865206368616e676520796f752066696c74687920616e696d616c",
                        "asm": "OP_RETURN 6b65657020746865206368616e676520796f752066696c74687920616e696d616c"
                    },
                    "spentTxId": null,
                    "spentIndex": null,
                    "spentHeight": null
                }
            ],
            "blockhash": "00000000440b89876c50059db146faefd279ed53b29ea91ccdfb0d5f690d958d",
            "blockheight": 1289141,
            "confirmations": 53666,
            "time": 1521978253,
            "blocktime": 1521978253,
            "valueOut": 0.7646881,
            "size": 299,
            "valueIn": 0.7647181,
            "fees": 0.00003
        }
    ]
}
```

<h2 id="tocRawTxObject">RawTxObject</h2>

<a id="schemerawtxobject"></a>

|Name|Type|Description|
|---|---|---|
|rawtx|String (HEX)|Raw transaction|

<a id="divider"></a>

> Example

```json
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

<h2 id="tocTxSendObject">TxSendObject</h2>

<a id="schemetxsendobject"></a>

|Name|Type|Description|
|---|---|---|
|txid|String (HEX)|HASH of transmitted/sent transaction on the blockchain|

<a id="divider"></a>

> Example

```json
{
  "txid": "c7736a0a0046d5a8cc61c8c3c2821d4d7517f5de2bc66a966011aaa79965ffba"
}
```

<h2 id="tocAddressObject">AddressObject</h2>

<a id="schemeaddressobject"></a>

|Name|Type|Description|
|---|---|---|
|addrStr|String|A string representing the address|
|balance|Float|Current balance of the address in BTC|
|balanceSat|Integer|Current balance of the address in satoshis|
|totalReceived|Float|Total amount in BTC received at the address|
|totalReceivedSat|Integer|Total amount in satoshis received at the address|
|totalSent|Float|Total amount in BTC sent from the address|
|totalSentSat|Integer|Total amount in satoshis sent from the address|
|unconfirmedBalance|Float|Unconfirmed balance of the address in BTC|
|unconfirmedBalanceSat|Integer|Unconfirmed balance of the address in satoshis|
|unconfirmedTxApperances|Integer|Number of unconfirmed transactions in which address participated|
|txApperances|Integer|Number of transactions in which address participated|
|transactions|Array of Strings|Array of transaction transactions in which address participated|

<a id="divider"></a>

> Example

```json
{
    "addrStr": "2N5DTRzmxKiJC3uuo39kqXTxhuSJQpoB3y2",
    "balance": 0.01,
    "balanceSat": 1000000,
    "totalReceived": 0.01,
    "totalReceivedSat": 1000000,
    "totalSent": 0,
    "totalSentSat": 0,
    "unconfirmedBalance": 0,
    "unconfirmedBalanceSat": 0,
    "unconfirmedTxApperances": 0,
    "txApperances": 1,
    "transactions": [
        "8ac4006d584b3a5302811b454f04a965d617520d9edcd02f5fc5d5c2d181766d"
    ]
}
```

<h2 id="tocUnspentOutputObject">UnspentOutputObject</h2>

<a id="schemeunspentoutputobject"></a>

|Name|Type|Description|
|---|---|---|
|address|String|A string representing the address|
|txid|String (HEX)|Hash of the transaction|
|vout|Integer|Index of the output|
|scriptPubKey|String (HEX)|Script public key|
|amount|Float|Total unspent amount in BTC|
|satoshis|Integer|Total unspent amount in satoshis|
|height|Integer|Height of the block in which the transaction is included|
|confirmations|Integer|Number of confirmations for the transaction|

<a id="divider"></a>

> Example

```json
[
    {
        "address": "2N5DTRzmxKiJC3uuo39kqXTxhuSJQpoB3y2",
        "txid": "8ac4006d584b3a5302811b454f04a965d617520d9edcd02f5fc5d5c2d181766d",
        "vout": 0,
        "scriptPubKey": "a914834be63f7d9d48ea1797cbe84282cdf4617246fc87",
        "amount": 0.01,
        "satoshis": 1000000,
        "height": 318135,
        "confirmations": 1024192
    }
]
```

<h2 id="tocPaymentForwardObject">PaymentForwardObject</h2>

<a id="schemepaymentforwardobject"></a>

|Name|Type|Description|
|---|---|---|
|paymentforward_id|String|Payment forward unique id|
|payment_address|String|String representing payment address. BTC received to payment address are automatically forwarded to destination address (and optionally to commission address in case one is specified in a predefined way during payment forward creation.) |
|destination_address|String|String representing destination address. BTC received at payment address will be forwarded to the destination address.|
|commission_address|String|String representing commission address. In case a commission address is specified part of the payment will be forwarded to this address each time a payment is received at payment address, based on predefined parameters (commission_fee_percent or commission_fee_satoshis)|
|commission_fee_percent|Float|Percentage of the payment which will be forwarded to commission address each time a payment is received at payment address. Min value 0.001. Max value 0.999. |
|commission_fee_satoshis|Integer|Fixed amount in satoshis which will be forwarded to commission address each time a payment is received at payment address.|
|created_date|String - Datetime in YYYY-MM-DDTHH:MM:SS.MMMZ format|Datetime of the creation of payment forward|
|callback_url|String|URL to which the notification about processed transactions is sent. Each time new payment is sent to payment address, notification is posted to this |
|mining_fee_satoshis|Integer|Mining fee for the payment forward transaction. Default is 10 000. Maximum is 150 000. Minimum is 10 000. In case of set commission_fee_percent, mining fee is subtracted from commission amount.|
|processed_txs|Array of [ProcessedTxObject](#schemeprocessedtxobject)|Array of processed transactions by the payment forward. In case of retrieving a list of payment forwards, this parameter is omitted.|

<a id="divider"></a>

> Example

```json
{
    "paymentforward_id": "CaVLNtcPuwN3uzGBYtQSSv7BEQJfT2jM",
    "payment_address": "mqiA4G8P5Gb2vfGutN97kJc36vSLWJYJrg",
    "destination_address": "2MxAS7QfBDQspHxmY4g4i92tLNTPH4r2DTZ",
    "commission_address": "2MuWUMWnWakRS59RrCHaY18hwjEj9RBaeuw",
    "commission_fee_percent": 0.1,
    "mining_fee_satoshis": 10000
}
```

<h2 id="tocProcessedTxObject">ProcessedTxObject</h2>

<a id="schemeprocessedtxobject"></a>

|Name|Type|Description|
|---|---|---|
|input_transaction_hash|String (HEX)|Hash of the input transaction. Input transaction is the transaction which occurs when a payment is sent to payment address.|
|received_amount_satoshis|Integer|Amount received to payment forward destination address in satoshis|
|transaction_hash|String (HEX)|Hash of the output transaction. Output transaction is the transaction which occurs when a payment is forwarded from payment address to destination address (and comission address in case one is specified for particular payment forward)|
|processed_date|String - Datetime in YYYY-MM-DDTHH:MM:SS.MMMZ format|Datetime when the payment was forwarded. |

<a id="divider"></a>

> Example

```json
{
    "input_transaction_hash":"6e3648463d26ee5af215fa3b61e976bf06cc7b1c6d2c034253967be65fc1c889",
    "received_amount_satoshis":5000000,
    "transaction_hash":"7c89d485e06f295de6fb1d676311340be35148dfc1a54de13b57e785227da78f",
    "processed_date":"2018-04-13T11:04:19.000Z"
}
```
