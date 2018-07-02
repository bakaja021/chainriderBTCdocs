# Transaction APIs

This set of APIs provides insight into the blockchain on a transaction level.

## Transaction by hash

<h3 id="getTransactionByHash">GET /tx/< tx_hash > </h3>

<a id="opIdGetTransactionByHash"></a>

*Get Transaction by hash*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tx_hash|path|String|True|Hash of the transaction|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TransactionObject](#schemetransactionobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>?token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
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
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
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
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
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
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
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
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
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
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/<TX_HASH>?token=<TOKEN>");
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
```

## Raw Transaction by hash

<h3 id="getRawTxByHash">GET /rawtx/< tx_hash > </h3>

<a id="opIdGetRawTxByHash"></a>

*Get Raw Transaction by hash*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tx_hash|path|String|True|Hash of the transaction|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RawTxObject](#schemerawtxobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>?token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/rawtx/<TX_HASH>?token=<TOKEN>");
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
    "rawtx": "010000000176fa2d692cce6b54c98ee80e9060d37c342a0bb49a9799efb7abff93470720bc01000000db00493046022100d4e2fba6e96007dba33776ac98f299194b7f6d712e2ab4a293f388fd18dbbeed02210091b7a3487b8230632aaf29ebcc8a5c49ddc07e24560ca2eec3fe39dfcfee384f0147304402203ea516845598b3c5b3a840f0577044312dc526ea67fb1a5d995ac7c5f2db0ae60220074b837bbf5590d709ebad9bba2a85d00e0b7e32a4d8f7601057623a1d0e546b0147522102632178d046673c9729d828cfee388e121f497707f810c131e0d3fc0fe0bd66d62103a0951ec7d3a9da9de171617026442fcd30f34d66100fab539853b43f508787d452aeffffffff0240420f000000000017a914834be63f7d9d48ea1797cbe84282cdf4617246fc8768f28e150100000017a9148ce5408cfeaddb7ccb2545ded41ef478109454848700000000"
}
```

## Transactions for Block

<h3 id="getTransactionsBlock">GET /txs</h3>

<a id="opIdGetTransactionsBlock"></a>

*Get Transactions for a Block*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|block|query|String|True|Block hash|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TxBlockObject](#schemetxblockobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?block=<BLOCK_HASH>&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
{
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
    ]
}
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?block=<BLOCK_HASH>&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
{
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
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

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?block=<BLOCK_HASH>&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
{
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
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

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs',
         params: {'block': <BLOCK_HASH>, 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
{
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
    ]
}
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs',
                  params={'block': <BLOCK_HASH>, 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
{
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
    ]
}
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?block=<BLOCK_HASH>&token=<TOKEN>");
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
    "pagesTotal": 3,
    "txs": [
        {
            "txid": "d614b789a22074c328e94f9fae7c1d9c56728bbdf5de614b0e34ae0d9339ca52",
            "version": 1,
            "locktime": 0,
            "vin": [
                {
                    "coinbase": "03b7da0402e004062f503253482f",
                    "sequence": 4294967295,
                    "n": 0
                }
            ],
            "vout": [
                {
                    "value": "25.00121110",
                    "n": 0,
                    "scriptPubKey": {
                        "hex": "2103bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2ac",
                        "asm": "03bf79df816d4016d9982f71c2783deb22750389c74a7e458bd192faa8b77937f2 OP_CHECKSIG",
                        "addresses": [
                            "mohFBEun8ojXxQNLNJYZELjCyYVyYv2x4n"
                        ],
                        "type": "pubkeyhash"
                    },
                    "spentTxId": "f2dfc507329a0a4c7eac2bc4ab9d4b3f1525169c8c9ea59d529e131f4f4930e2",
                    "spentIndex": 178,
                    "spentHeight": 318556
                }
            ],
            "blockhash": "000000004da178abfd3798dcaa3111c2e145d654fad364bd20214cef9f80ab6e",
            "blockheight": 318135,
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "isCoinBase": true,
            "valueOut": 25.0012111,
            "size": 109
        },
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
            "confirmations": 1030747,
            "time": 1421145649,
            "blocktime": 1421145649,
            "valueOut": 46.57657,
            "size": 334,
            "valueIn": 46.57658,
            "fees": 0.00001
        }
    ]
}
```

## Transactions for Address

<h3 id="getTransactionsAddress">GET /txs</h3>

<a id="opIdGetTransactionsAddress"></a>

*Get Transactions for an Address*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|String|True|Address string|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TxBlockObject](#schemetxblockobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?address=<ADDRESS>&token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
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
```

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?address=<ADDRESS>&token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
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

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?address=<ADDRESS>&token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
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
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs',
         params: {'address': <ADDRESS>, 'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
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
```

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs',
                  params={'address': <ADDRESS>, 'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
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
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/txs?address=<ADDRESS>&token=<TOKEN>");
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
```

## Transactions for multiple Addresses - GET

<h3 id="getTransactionsAddresses">GET /addrs/< address1 >,< address2 >,...,< addressn >/txs</h3>

<a id="opIdGetTransactionsAddresses"></a>

*Get Transactions for multiple Addresses*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|addr|path|String Aray(address)|True|Array of comma separated address strings|
|from|query|Integer|False|Starting number of tx|
|to|query|Integer|False|Ending number of tx|
|noAsm|query|Integer|False|Default is 0. If set to 1 Asm info will be ommitted for tx.|
|noScriptSig|query|Integer|False|Default is 0. If set to 1 Script Signature info will be ommitted for tx.|
|noSpent|query|Integer|False|Default is 0. If set to 1 Spent info will be ommitted for tx.|
|token|query|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TxAddressesObject](#schemetxaddressesobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X GET https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs?token=<TOKEN> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

# Response example
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

```php
<?php
$URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs?token=<TOKEN>";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Content-Type: application/json\r\nAccept: application/json\r\n";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);

// Response example
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
?>
```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs?token=<TOKEN>',
  method: 'get',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
});

// Response example
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
}

result = RestClient.get 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs',
         params: {'token': <TOKEN>}, headers: headers

p JSON.parse(result)

# Response example
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

```python
import requests

headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
}

r = requests.get('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs',
                  params={'token': <TOKEN>}, headers = headers)

print r.json()

# Response example
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

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/<ADDRESS1>,<ADDRESS2>,..,<ADDRESSn>/txs?token=<TOKEN>");
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

## Transactions for multiple Addresses - POST

<h3 id="postTransactionsAddresses">POST /addrs/txs </h3>

<a id="opIdpostTransactionsAddresses"></a>

*Get Transactions for multiple Addresses by using POST method*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|addrs|body|String Aray(address)|True|Array of comma separated address strings|
|from|body|Integer|False|Starting number of tx|
|to|body|Integer|False|Ending number of tx|
|noAsm|body|Integer|False|Default is 0. If set to 1 Asm info will be ommitted for tx.|
|noScriptSig|body|Integer|False|Default is 0. If set to 1 Script Signature info will be ommitted for tx.|
|noSpent|body|Integer|False|Default is 0. If set to 1 Spent info will be ommitted for tx.|
|token|body|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TxAddressesObject](#schemetxaddressesobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X POST https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -D '<body_here>'
```

```php
<?php
    $body="<body_here>";
    $opts = array('http' =>
      array(
        'method'  => 'POST',
        'header'  => Content-Type: application/json\r\nAccept: application/json\r\n",
        'content' => $body
      )
    );
    $context  = stream_context_create($opts);
    $URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs";
    $result = file_get_contents($url, false, $context, -1, 40000);
);


$context = stream_context_create($aHTTP);
    $response = file_get_contents($URL, false, $context);
?>

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
};

var requestBody=<body_here>

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs',
  method: 'POST',
  headers: headers,
  data: requestBody,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs',
         payload:<body_here>, headers: headers

p JSON.parse(result)
```

```python
import requests

headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs',
                  data=<body_here>, params={}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/addrs/txs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setDoOutput(true);
con.setRequestMethod("POST");
OutputStream os = con.getOutputStream();
OutputStreamWriter osw = new OutputStreamWriter(os, "UTF-8");
osw.write("<body_here>");
osw.flush();
osw.close();
os.close();  //don't forget to close the OutputStream
httpCon.connect();


//read the inputstream and print it
String result;
BufferedInputStream bis = new BufferedInputStream(con.getInputStream());
ByteArrayOutputStream buf = new ByteArrayOutputStream();
int result2 = bis.read();
while(result2 != -1) {
    buf.write((byte) result2);
    result2 = bis.read();
}
result = buf.toString();
System.out.println(result);
```

> Body parameter


```json
{
"addrs": "2N5DTRzmxKiJC3uuo39kqXTxhuSJQpoB3y2,2N66DDrmjDCMM3yMSYtAQyAqRtasSkFhbmX",
"token": <TOKEN>
}
```

> Example response

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

## Send Raw Transaction

<h3 id="sendRawTx">POST /tx/send </h3>

<a id="opIdSendRawTx"></a>

*Send/broadcast Raw Transaction*

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|rawtx|body|String|True|Raw signed transaction as hex string|
|token|body|String|True|Token obtained from the ChainRider service|

<h3 id="response">Response</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TxSendObject](#schemetxsendobject)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<a id="divider"></a>

> Code samples

```shell
curl -X POST https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -D '<body_here>'
```

```php
<?php
    $body="<body_here>";
    $opts = array('http' =>
      array(
        'method'  => 'POST',
        'header'  => Content-Type: application/json\r\nAccept: application/json\r\n",
        'content' => $body
      )
    );
    $context  = stream_context_create($opts);
    $URL = "https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send";
    $result = file_get_contents($url, false, $context, -1, 40000);
);


$context = stream_context_create($aHTTP);
    $response = file_get_contents($URL, false, $context);
?>

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
};

var requestBody=<body_here>

$.ajax({
  url: 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send',
  method: 'POST',
  headers: headers,
  data: requestBody,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send',
         payload:<body_here>, headers: headers

p JSON.parse(result)
```

```python
import requests

headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send',
                  data=<body_here>, params={}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.chainrider.io/v1/<DIGITAL_CURRENCY>/<BLOCKCHAIN>/tx/send");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestProperty("Accept", "application/json");
con.setRequestProperty("Content-Type", "application/json");
con.setDoOutput(true);
con.setRequestMethod("POST");
OutputStream os = con.getOutputStream();
OutputStreamWriter osw = new OutputStreamWriter(os, "UTF-8");
osw.write("<body_here>");
osw.flush();
osw.close();
os.close();  //don't forget to close the OutputStream
httpCon.connect();


//read the inputstream and print it
String result;
BufferedInputStream bis = new BufferedInputStream(con.getInputStream());
ByteArrayOutputStream buf = new ByteArrayOutputStream();
int result2 = bis.read();
while(result2 != -1) {
    buf.write((byte) result2);
    result2 = bis.read();
}
result = buf.toString();
System.out.println(result);
```

> Body parameter


```json
{
  "rawtx": "01000000017b1eabe0209b1fe794124575ef807057c77ada2138ae4fa8d6c4de0398a14f3f00000000494830450221008949f0cb400094ad2b5eb399d59d01c14d73d8fe6e96df1a7150deb388ab8935022079656090d7f6bac4c9a94e0aad311a4268e082a725f8aeae0573fb12ff866a5f01ffffffff01f0ca052a010000001976a914cbc20a7664f2f69e5355aa427045bc15e7c6c77288ac00000000",
  "token": <TOKEN>
}
```

> Example response

```json
{
  "txid": "c7736a0a0046d5a8cc61c8c3c2821d4d7517f5de2bc66a966011aaa79965ffba"
}
```
