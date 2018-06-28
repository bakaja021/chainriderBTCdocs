# Blockchain APIs

The set of APIs below provides insight into the network status and general information about the corresponding blockchain selected by specifying endpoint for digital currency and blockchain type.

## General information

<h3 id="getBlockchainInfo">GET /status</h3>

<a id="opIdGetBlockchainInfo"></a>

*Get general information about the blockchain.*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|q|query|String|True|Please use `geInfo` as value|
|token|query|String|True|Token obtained from the ChainRider service|


<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BlockchainInfoObject](#schemeblockchaininfoobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getInfo&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
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

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getInfo&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
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
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getInfo&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
         params: {'q': 'getInfo', 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
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

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
                  params={'q': 'getInfo', 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
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

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getInfo&token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

// Response example
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


## Current difficulty

<h3 id="getBlockchainDifficulty">GET /status</h3>

<a id="opIdGetBlockchainDifficulty"></a>

*Get current difficulty for the blockchain.*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|q|query|String|True|Please use `getDifficulty` as value|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BlockchainDifficultyObject](#schemeblockchaindifficultyobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getDifficulty&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "difficulty":91708039.52534924
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getDifficulty&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "difficulty":91708039.52534924
}
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getDifficulty&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "difficulty":91708039.52534924
}
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
         params: {'q': 'getDifficulty', 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "difficulty":91708039.52534924
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
                  params={'q': 'getDifficulty', 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "difficulty":91708039.52534924
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getDifficulty&token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

// Response example
{
    "difficulty":91708039.52534924
}
```

## Best Block hash

<h3 id="getBlockchainBestBlock">GET /status</h3>

<a id="opIdGetBlockchainBestBlock"></a>

*Get best block hash for the blockchain.*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|q|query|String|True|Please use `getBestBlockHash` as value|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BlockchainBestBlockObject](#schemeblockchainbestblockobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getBestBlockHash&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getBestBlockHash&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getBestBlockHash&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
         params: {'q': 'getBestBlockHash', 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
                  params={'q': 'getBestBlockHash', 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getBestBlockHash&token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

// Response example
{
    "bestblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

## Last Block hash

<h3 id="getBlockchainLastBlock">GET /status</h3>

<a id="opIdGetBlockchainLastBlock"></a>

*Get last block hash for the blockchain.*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|q|query|String|True|Please use `getLastBlockHash` as value|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BlockchainLastBlockObject](#schemeblockchainlastblockobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getLastBlockHash&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getLastBlockHash&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getLastBlockHash&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
         params: {'q': 'getLastBlockHash', 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status',
                  params={'q': 'getLastBlockHash', 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/status?q=getLastBlockHash&token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

// Response example
{
    "syncTipHash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595",
    "lastblockhash":"00000000000000188d9e69d1db6f8a03361785b3eab26baa349223c8192d5595"
}
```

## Blockchain Data Sync status

<h3 id="getBlockchainDataSync">GET /sync</h3>

<a id="opIdGetBlockchainDataSync"></a>

*Get blockchain data sync status*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BlockchainDataSyncObject](#schemeblockchaindatasyncobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync?token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/sync?token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

// Response example
{
    "status":"finished",
    "blockChainHeight":894442,
    "syncPercentage":100,
    "height":894442,
    "error":null,
    "type":"bitcore node"
}
```
