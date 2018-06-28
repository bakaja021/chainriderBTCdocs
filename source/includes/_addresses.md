# Address APIs

This set of APIs provides insight into the blockchain on a transaction level.

## Address by hash

<h3 id="getAddressByHash">GET /addr/< address > </h3>

<a id="opIdGetAddressByHash"></a>

*Get Address by hash*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|String|True|Address string|
|noTxList|query|Integer|False|Default 0; If set to 1 transaction list will be ommitted.|
|from|query|Integer|False|Start transaction in the address tx list; Default 0|
|to|query|Integer|False|End transaction in the address tx list|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AddressObject](#schemeaddressobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>?token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
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

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
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
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
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

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
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

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>?token=<TOKEN>");
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

## Address Balance

<h3 id="getAddressBalanceByHash">GET /addr/< address >/balance </h3>

<a id="opIdGetAddressBalanceByHash"></a>

*Get Address balance in duffs*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|String|True|Address string|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Integer representing balance in duffs|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance?token=<TOKEN> \
  -H 'Content-Type: application/json'

# Response example
0
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
0
?>
```

```javascript
var headers = {
  'Content-Type':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
1000000
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
1000000
```

```python
import requests

headers = {
  'Content-Type':'application/json'
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
1000000
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/balance?token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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
1000000
```

## Address Total Received

<h3 id="getAddressTotalReceivedByHash">GET /addr/< address >/totalReceived </h3>

<a id="opIdGetAddressTotalReceivedByHash"></a>

*Get Total Received amount in duffs for an Address*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|String|True|Address string|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Integer representing total received amount in duffs|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived?token=<TOKEN> \
  -H 'Content-Type: application/json'

# Response example
1000000
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
1000000
?>
```

```javascript
var headers = {
  'Content-Type':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
1000000
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
1000000
```

```python
import requests

headers = {
  'Content-Type':'application/json'
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
1000000
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalReceived?token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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
1000000
```

## Address Total Sent

<h3 id="getAddressTotalSentByHash">GET /addr/< address >/totalSent </h3>

<a id="opIdGetAddressTotalSentByHash"></a>

*Get Total Sent amount in duffs for an Address*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|String|True|Address string|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Integer representing total sent amount in duffs|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent?token=<TOKEN> \
  -H 'Content-Type: application/json'

# Response example
0
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
0
?>
```

```javascript
var headers = {
  'Content-Type':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
0
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
0
```

```python
import requests

headers = {
  'Content-Type':'application/json'
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
0
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/totalSent?token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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
0
```

## Address Unconfirmed Balance

<h3 id="getAddressUnconfirmedBalanceByHash">GET /addr/< address >/unconfirmedBalance </h3>

<a id="opIdGetAddressUnconfirmedBalanceByHash"></a>

*Get Unconfirmed Balance for an Address*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|String|True|Address string|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Integer representing unconfirmed balance in duffs|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance?token=<TOKEN> \
  -H 'Content-Type: application/json'

# Response example
0
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
0
?>
```

```javascript
var headers = {
  'Content-Type':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
0
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
0
```

```python
import requests

headers = {
  'Content-Type':'application/json'
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
0
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addr/<ADDRESS>/unconfirmedBalance?token=<TOKEN>");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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
0
```
