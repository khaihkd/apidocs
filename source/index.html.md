---
title: Tomochain APIs
language_tabs:
  - shell: cURL
  - node: Node.js
  - go: GO
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="tomochain-apis">TomoChain APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Happy to code TomoChain APIs

License: <a href="https://github.com/tomochain/tomochain">Github</a>


<!-- Generator: Widdershins v3.6.6 -->

<h1 id="tomochain-json-rpc">Tomochain JSON-RPC v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

A collection holding all the Tomochain JSON​ RPC API calls

Base URLs:

* <a href="https://rpc.tomochain.com">https://rpc.tomochain.com</a>

<h1 id="tomochain-json-rpc-web3">web3</h1>

API for web3 request

## clientRequest

<a id="opIdclientRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/clientVersion \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/clientVersion",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'web3_clientVersion',
  params: [],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/clientVersion"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/clientVersion")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/clientVersion", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/clientVersion")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /clientVersion`

Returns the current client version.

**Parameters**

none

**Returns**

`String` - The current client version

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "web3_clientVersion",
  "params": [],
  "id": 1
}
```

<h3 id="clientrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[clientVersionRequest](#schemaclientversionrequest)|true|none|

<h3 id="clientrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sha3Request

<a id="opIdsha3Request"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/sha3 \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"web3_sha3","params":["0x68656c6c6f20776f726c64"],"id":64}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/sha3",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'web3_sha3',
  params: [ '0x68656c6c6f20776f726c64' ],
  id: 64 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/sha3"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/sha3")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/sha3", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/sha3")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}")
  .asString();
```

`POST /sha3`

Returns Keccak-256 (not the standardized SHA3-256) of the given data.

**Parameters**

- `DATA` - the data to convert into a SHA3 hash

`params:` `[
  "0x68656c6c6f20776f726c64"
]`

**Returns**

`DATA` - The SHA3 result of the given string.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "web3_sha3",
  "params": [
    "0x68656c6c6f20776f726c64"
  ],
  "id": 64
}
```

<h3 id="sha3request-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sha3request](#schemasha3request)|true|none|

<h3 id="sha3request-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-net">net</h1>

API for network request

## versionRequest

<a id="opIdversionRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/version \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_version","params":[],"id":67}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/version",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'net_version', params: [], id: 67 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/version"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/version")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/version", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/version")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /version`

Returns the current network id.

**Parameters**

none

**Returns**

- `String` - The current network id.

  - `"88"`: Tomochain Mainnet

  - `"89"`: Tomochain Testnet

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_version",
  "params": [],
  "id": 67
}
```

<h3 id="versionrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[versionrequest](#schemaversionrequest)|true|none|

<h3 id="versionrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## listeningRequest

<a id="opIdlisteningRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/listening \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_listening","params":[],"id":67}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/listening",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'net_listening', params: [], id: 67 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/listening"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/listening")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/listening", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/listening")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /listening`

Returns `true` if client is actively listening for network connections.

**Parameters**

none

**Returns**

- `Boolean` - `true` when listening, otherwise `false`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_listening",
  "params": [],
  "id": 67
}
```

<h3 id="listeningrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listeningrequest](#schemalisteningrequest)|true|none|

<h3 id="listeningrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## peerCountRequest

<a id="opIdpeerCountRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/peerCount \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_peerCount","params":[],"id":74}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/peerCount",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'net_peerCount', params: [], id: 74 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/peerCount"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/peerCount")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/peerCount", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/peerCount")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}")
  .asString();
```

`POST /peerCount`

Returns number of peers currently connected to the client.

**Parameters**

none

**Returns**

- `QUANTITY` - integer of the number of connected peers.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_peerCount",
  "params": [],
  "id": 74
}
```

<h3 id="peercountrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[peerCountRequest](#schemapeercountrequest)|true|none|

<h3 id="peercountrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-eth">eth</h1>

API for eth information

## protocolVersionRequest

<a id="opIdprotocolVersionRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/protocolVersion \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_protocolVersion","params":[],"id":67}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/protocolVersion",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_protocolVersion',
  params: [],
  id: 67 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/protocolVersion"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/protocolVersion")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/protocolVersion", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/protocolVersion")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /protocolVersion`

Returns the current ethereum protocol version.

**Parameters**

none

**Returns**

- `String` - The current ethereum protocol version

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_protocolVersion",
  "params": [],
  "id": 67
}
```

<h3 id="protocolversionrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[protocolVersionRequest](#schemaprotocolversionrequest)|true|none|

<h3 id="protocolversionrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## syncingrequest

<a id="opIdsyncingrequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/syncing \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/syncing",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'eth_syncing', params: [], id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/syncing"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/syncing")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/syncing", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/syncing")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /syncing`

Returns an object with data about the sync status or false.

**Parameters**

none

**Returns**

- `Object|Boolean`, An object with sync status data or FALSE, when not syncing:

  - `startingBlock`: `QUANTITY` - The block at which the import started (will only be reset, after the sync reached his head)

  - `currentBlock`: `QUANTITY` - The current block, same as eth_blockNumber

  - `highestBlock`: `QUANTITY` - The estimated highest block

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_syncing",
  "params": [],
  "id": 1
}
```

<h3 id="syncingrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[syncingrequest](#schemasyncingrequest)|true|none|

<h3 id="syncingrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## coinbase

<a id="opIdcoinbase"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/coinbase \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_coinbase","params":[],"id":64}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/coinbase",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'eth_coinbase', params: [], id: 64 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/coinbase"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/coinbase")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/coinbase", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/coinbase")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}")
  .asString();
```

`POST /coinbase`

Returns the client coinbase address.
**Parameters**
none
**Returns**
- `DATA`, 20 bytes - the current coinbase address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_coinbase",
  "params": [],
  "id": 64
}
```

<h3 id="coinbase-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[coinbaserequest](#schemacoinbaserequest)|true|none|

<h3 id="coinbase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## gasPrice

<a id="opIdgasPrice"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/gasPrice \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":73}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/gasPrice",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'eth_gasPrice', params: [], id: 73 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/gasPrice"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/gasPrice")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/gasPrice", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/gasPrice")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}")
  .asString();
```

`POST /gasPrice`

Returns the current price per gas in wei.
**Parameters**
none
**Returns**
- `QUANTITY` - integer of the current gas price in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_gasPrice",
  "params": [],
  "id": 73
}
```

<h3 id="gasprice-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[gasPriceRequest](#schemagaspricerequest)|true|none|

<h3 id="gasprice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## accounts

<a id="opIdaccounts"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/accounts \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_accounts","params":[],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/accounts",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'eth_accounts', params: [], id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/accounts"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/accounts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/accounts", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/accounts")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /accounts`

Returns a list of addresses owned by client.

**Parameters**

none

**Returns**

- `Array of DATA`, 20 Bytes - addresses owned by the client

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_accounts",
  "params": [],
  "id": 1
}
```

<h3 id="accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[accountsrequest](#schemaaccountsrequest)|true|none|

<h3 id="accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## blockNumber

<a id="opIdblockNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/blockNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":83}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/blockNumber",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0', method: 'eth_blockNumber', params: [], id: 83 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/blockNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/blockNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/blockNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/blockNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}")
  .asString();
```

`POST /blockNumber`

Returns the number of most recent block.
**Parameters**
none
**Returns**
- `QUANTITY` - integer of the current block number the client is on.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_blockNumber",
  "params": [],
  "id": 83
}
```

<h3 id="blocknumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[blockNumberRequest](#schemablocknumberrequest)|true|none|

<h3 id="blocknumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBalance

<a id="opIdgetBalance"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBalance \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x2b5634c42055806a59e9107ed44d43c426e58258","latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBalance",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBalance',
  params: [ '0x2b5634c42055806a59e9107ed44d43c426e58258', 'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBalance"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBalance")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBalance", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBalance")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getBalance`

Returns the balance of the account of given address.

**Parameters**

- `DATA`, 20 Bytes - address to check for balance.
- `QUANTITY|TAG` - integer block number, or the string "latest", "earliest" or "pending", see the default block parameter

      params: [
        ' 0x2b5634c42055806a59e9107ed44d43c426e58258',
        'latest'
      ]

**Returns**
- `QUANTITY` - integer of the current balance in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBalance",
  "params": [
    "0x2b5634c42055806a59e9107ed44d43c426e58258",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getbalance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBalanceRequest](#schemagetbalancerequest)|true|none|

<h3 id="getbalance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getStorageAt

<a id="opIdgetStorageAt"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getStorageAt \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getStorageAt","params":["0x295a70b2de5e3953354a6a8344e616ed314d7251","0x0","latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getStorageAt",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getStorageAt',
  params: [ '0x295a70b2de5e3953354a6a8344e616ed314d7251', '0x0', 'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getStorageAt"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getStorageAt")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getStorageAt", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getStorageAt")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getStorageAt`

Returns the balance of the account of given address.

**Parameters**

- `DATA`, 20 Bytes - address to check for balance.

- `QUANTITY|TAG` - integer block number, or the string "latest", "earliest" or "pending", see the default block parameter

      params: [
            '0x2b5634c42055806a59e9107ed44d43c426e58258',
            'latest'
            ]

**Returns**

- `QUANTITY` - integer of the current balance in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getStorageAt",
  "params": [
    "0x295a70b2de5e3953354a6a8344e616ed314d7251",
    "0x0",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getstorageat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getStorageAtRequest](#schemagetstorageatrequest)|true|none|

<h3 id="getstorageat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionCount

<a id="opIdgetTransactionCount"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getTransactionCount \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionCount","params":["0xbf1dcb735e512b731abd3404c15df6431bd03d42","latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getTransactionCount",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getTransactionCount',
  params: [ '0xbf1dcb735e512b731abd3404c15df6431bd03d42', 'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getTransactionCount"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getTransactionCount")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getTransactionCount", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getTransactionCount")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getTransactionCount`

Returns the number of transactions sent from an address.

**Parameters**

- `DATA`, 20 Bytes - address.
- `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

      params: [
        '0x407d73d8a49eeb85d32cf465507dd71d507100c1',
        'latest' // state at the latest block
      ]

**Returns**

- `QUANTITY` - integer of the number of transactions send from this address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionCount",
  "params": [
    "0xbf1dcb735e512b731abd3404c15df6431bd03d42",
    "latest"
  ],
  "id": 1
}
```

<h3 id="gettransactioncount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionCountRequest](#schemagettransactioncountrequest)|true|none|

<h3 id="gettransactioncount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockTransactionCountByHash

<a id="opIdgetBlockTransactionCountByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockTransactionCountByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockTransactionCountByHash","params":["0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockTransactionCountByHash",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockTransactionCountByHash',
  params: 
   [ '0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockTransactionCountByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockTransactionCountByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockTransactionCountByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockTransactionCountByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}")
  .asString();
```

`POST /getBlockTransactionCountByHash`

Returns the number of transactions in a block from a block matching the given block hash.

**Parameters**

- `DATA`, 32 Bytes - hash of a block

    params: [
      '0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34'
    ]

**Returns**

- `QUANTITY` - integer of the number of transactions in this block.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByHash",
  "params": [
    "0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"
  ],
  "id": 1
}
```

<h3 id="getblocktransactioncountbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockTransactionCountByHashRequest](#schemagetblocktransactioncountbyhashrequest)|true|none|

<h3 id="getblocktransactioncountbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockTransactionCountByNumber

<a id="opIdgetBlockTransactionCountByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockTransactionCountByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockTransactionCountByNumber","params":["0x52A8CA"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockTransactionCountByNumber",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockTransactionCountByNumber',
  params: [ '0x52A8CA' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockTransactionCountByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockTransactionCountByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockTransactionCountByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockTransactionCountByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}")
  .asString();
```

`POST /getBlockTransactionCountByNumber`

Returns the number of transactions in a block matching the given block number.

**Parameters**

- `QUANTITY|TAG` - integer of a block number, or the string `"earliest"`, `"latest"` or `"pending"`, as in the default block parameter.

    params: [
      '0x85', // 232
    ]

**Returns**

- `QUANTITY` - integer of the number of transactions in this block.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByNumber",
  "params": [
    "0x52A8CA"
  ],
  "id": 1
}
```

<h3 id="getblocktransactioncountbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockTransactionCountByNumberRequest](#schemagetblocktransactioncountbynumberrequest)|true|none|

<h3 id="getblocktransactioncountbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCode

<a id="opIdgetCode"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getCode \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCode","params":["0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b","0x2"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getCode",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getCode',
  params: [ '0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b', '0x2' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getCode"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getCode")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getCode", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getCode")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}")
  .asString();
```

`POST /getCode`

Returns code at a given address.

**Parameters**

- `DATA`, 20 Bytes - address

- `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

    params: [
      '0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b',
      '0x2'  // 2
    ]

**Returns**

- `DATA` - the code from the given address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCode",
  "params": [
    "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
    "0x2"
  ],
  "id": 1
}
```

<h3 id="getcode-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCodeRequest](#schemagetcoderequest)|true|none|

<h3 id="getcode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sign

<a id="opIdsign"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/sign \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sign","params":["0x9b2055d370f73ec7d8a03e965129118dc8f5bf83","0xdeadbeaf"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/sign",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_sign',
  params: [ '0x9b2055d370f73ec7d8a03e965129118dc8f5bf83', '0xdeadbeaf' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/sign"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/sign")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/sign", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/sign")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}")
  .asString();
```

`POST /sign`

The sign method calculates an Ethereum specific signature with: `sign(keccak256("\x19Ethereum Signed Message:\n" + len(message) + message)))`.

By adding a prefix to the message makes the calculated signature recognisable as an Ethereum specific signature.  This prevents misuse where a malicious DApp can sign arbitrary data (e.g. transaction) and use the signature to impersonate the victim.

**Note:** the address to sign with must be unlocked.

**Parameters**

  - `DATA`, 20 Bytes - address

  - `DATA`, N Bytes - message to sign

**Returns**

- `DATA`: Signature

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sign",
  "params": [
    "0x9b2055d370f73ec7d8a03e965129118dc8f5bf83",
    "0xdeadbeaf"
  ],
  "id": 1
}
```

<h3 id="sign-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[signrequest](#schemasignrequest)|true|none|

<h3 id="sign-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sendTransaction

<a id="opIdsendTransaction"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/sendTransaction \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"}],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/sendTransaction",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_sendTransaction',
  params: 
   [ { from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
       to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
       gas: '0x76c0',
       gasPrice: '0x9184e72a000',
       value: '0x9184e72a',
       data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675' } ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/sendTransaction"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/sendTransaction")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/sendTransaction", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/sendTransaction")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")
  .asString();
```

`POST /sendTransaction`

Creates new message call transaction or a contract creation, if the data field contains code.

**Parameters**

`Object` - The transaction object

  - `from`: `DATA`, 20 Bytes - The address the transaction is send from.

  - `to`: `DATA`, 20 Bytes - (optional when creating new contract) The address the transaction is directed to.

  - `gas`: `QUANTITY` - (optional, default: 90000) Integer of the gas provided for the transaction execution. It will return unused gas.

  - `gasPrice`: `QUANTITY` - (optional, default: To-Be-Determined) Integer of the gasPrice used for each paid gas

  - `value`: `QUANTITY` - (optional) Integer of the value sent with this transaction

  - `data`: `DATA` - The compiled code of a contract OR the hash of the invoked method signature and encoded parameters. For details see Ethereum Contract ABI

  - `nonce`: `QUANTITY` - (optional) Integer of a nonce. This allows to overwrite your own pending transactions that use the same nonce.

    params: [{
      "from": " 0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": " 0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0", // 30400
      "gasPrice": "0x9184e72a000", // 10000000000000
      "value": "0x9184e72a", // 2441406250
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }]

**Returns**
- `DATA`, 32 Bytes - the transaction hash, or the zero hash if the transaction is not yet available.

 Use `eth_getTransactionReceipt` to get the contract address, after the transaction was mined, when you created a contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendTransaction",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}
```

<h3 id="sendtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sendTransactionRequest](#schemasendtransactionrequest)|true|none|

<h3 id="sendtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sendRawTransaction

<a id="opIdsendRawTransaction"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/sendRawTransaction \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sendRawTransaction","params":["0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/sendRawTransaction",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_sendRawTransaction',
  params: 
   [ '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/sendRawTransaction"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/sendRawTransaction")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/sendRawTransaction", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/sendRawTransaction")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}")
  .asString();
```

`POST /sendRawTransaction`

Creates new message call transaction or a contract creation for signed transactions.

**Parameters**

- `DATA`, The signed transaction data.

    params: ["0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"]

**Returns**

- `DATA`, 32 Bytes - the transaction hash, or the zero hash if the transaction is not yet available.

Use `eth_getTransactionReceipt` to get the contract address, after the transaction was mined, when you created a contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendRawTransaction",
  "params": [
    "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
  ],
  "id": 1
}
```

<h3 id="sendrawtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sendRawTransactionRequest](#schemasendrawtransactionrequest)|true|none|

<h3 id="sendrawtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## call

<a id="opIdcall"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/call \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_call","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"},"latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/call",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_call',
  params: 
   [ { from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
       to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
       gas: '0x76c0',
       gasPrice: '0x9184e72a000',
       value: '0x9184e72a',
       data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675' },
     'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/call"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/call")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/call", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/call")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}")
  .asString();
```

`POST /call`

Executes a new message call immediately without creating a transaction on the block chain.

**Parameters**

`Object` [required]- The transaction call object

  - `from`: `DATA`, 20 Bytes - (optional) The address the transaction is sent from.

  - `to`: `DATA`, 20 Bytes - The address the transaction is directed to.

  - `gas`: `QUANTITY` - (optional) Integer of the gas provided for the transaction execution. eth_call consumes zero gas, but this parameter may be needed by some executions.

  - `gasPrice`: `QUANTITY` - (optional) Integer of the gasPrice used for each paid gas

  - `value`: `QUANTITY` - (optional) Integer of the value sent with this transaction

  - `data`: `DATA` - (optional) Hash of the method signature and encoded parameters. For details see Ethereum Contract ABI

  - `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

**Returns**
- `DATA` - the return value of executed contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_call",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    },
    "latest"
  ],
  "id": 1
}
```

<h3 id="call-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[callrequest](#schemacallrequest)|true|none|

<h3 id="call-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## estimateGas

<a id="opIdestimateGas"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/estimateGas \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_estimateGas","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"}],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/estimateGas",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_estimateGas',
  params: 
   [ { from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
       to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
       gas: '0x76c0',
       gasPrice: '0x9184e72a000',
       value: '0x9184e72a',
       data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675' } ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/estimateGas"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/estimateGas")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/estimateGas", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/estimateGas")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")
  .asString();
```

`POST /estimateGas`

Generates and returns an estimate of how much gas is necessary to allow the transaction to complete.  The transaction will not be added to the blockchain. Note that the estimate may be significantly more  than the amount of gas actually used by the transaction, for a variety of reasons including EVM mechanics and node performance.

**Parameters**

See `eth_call` parameters, expect that all properties are optional. If no gas limit is specified geth uses  the block gas limit from the pending block as an upper bound. As a result the returned estimate might not be  enough to executed the call/transaction when the amount of gas is higher than the pending block gas limit.

**Returns**
- `QUANTITY` - the amount of gas used.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_estimateGas",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}
```

<h3 id="estimategas-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[estimateGasRequest](#schemaestimategasrequest)|true|none|

<h3 id="estimategas-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockByHash

<a id="opIdgetBlockByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockByHash","params":["0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",true],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockByHash",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockByHash',
  params: 
   [ '0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624',
     true ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}")
  .asString();
```

`POST /getBlockByHash`

Returns information about a block by hash.

**Parameters**

- `BLOCKHASH` [required] - a string representing a BLOCKHASH
- `Boolean` [required] - If true it returns the full transaction objects, if false only the hashes of the transactions.

    params: [
      '0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624',
      true
    ]

**Returns**
`Object` - A block object, or null when no block was found:

  - `number`: `QUANTITY` - the block number. null when its pending block.

  - `hash`: `DATA`, 32 Bytes - hash of the block. `null` when its pending block.

  - `parentHash`: `DATA`, 32 Bytes - hash of the parent block.

  - `nonce`: `DATA`, 8 Bytes - hash of the generated proof-of-work. `null` when its pending block.

  - `sha3Uncles`: `DATA`, 32 Bytes - SHA3 of the uncles data in the block.

  - `logsBloom`: `DATA`, 256 Bytes - the bloom filter for the logs of the block. `null` when its pending block.

  - `transactionsRoot`: `DATA`, 32 Bytes - the root of the transaction trie of the block.

  - `stateRoot`: `DATA`, 32 Bytes - the root of the final state trie of the block.

  - `receiptsRoot`: `DATA`, 32 Bytes - the root of the receipts trie of the block.

  - `miner`: `DATA`, 20 Bytes - the address of the beneficiary to whom the mining rewards were given.

  - `difficulty`: `QUANTITY` - integer of the difficulty for this block.

  - `totalDifficulty`: `QUANTITY` - integer of the total difficulty of the chain until this block.

  - `extraData`: `DATA` - the "extra data" field of this block.

  - `size`: `QUANTITY` - integer the size of this block in bytes.

  - `gasLimit`: `QUANTITY` - the maximum gas allowed in this block.

  - `gasUsed`: `QUANTITY` - the total used gas by all transactions in this block.

  - `timestamp`: `QUANTITY` - the unix timestamp for when the block was collated.

  - `transactions`: `Array` - Array of transaction objects, or 32 Bytes transaction hashes depending on the last given parameter.

  - `uncles`: `Array` - Array of uncle hashes.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByHash",
  "params": [
    "0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",
    true
  ],
  "id": 1
}
```

<h3 id="getblockbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockByHashRequest](#schemagetblockbyhashrequest)|true|none|

<h3 id="getblockbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockByNumber

<a id="opIdgetBlockByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockByNumber","params":["0x0",true],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockByNumber",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockByNumber',
  params: [ '0x0', true ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}")
  .asString();
```

`POST /getBlockByNumber`

Returns information about a block by block number.

**Parameters**

`BLOCKNUMBER` [required] - a hex code of an integer representing the BLOCKNUMBER or one of the following special params:
  
  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

`FULLTX` [required] - a boolean value specified whether you want to get transactions list or not

    params: [
      '0x0',
      true
    ]

**Returns**

- `RETURN VALUE` - block data of the given `BLOCKNUMBER`

See `eth_getBlockByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": [
    "0x0",
    true
  ],
  "id": 1
}
```

<h3 id="getblockbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockByNumberRequest](#schemagetblockbynumberrequest)|true|none|

<h3 id="getblockbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockSignersByNumber

<a id="opIdgetBlockSignersByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockSignersByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockSignersByNumber","params":["0xA61F98"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockSignersByNumber",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockSignersByNumber',
  params: [ '0xA61F98' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockSignersByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockSignersByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockSignersByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockSignersByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")
  .asString();
```

`POST /getBlockSignersByNumber`

Returns the signers set of the block of given `BLOCKNUMBER`.

**Parameters**

`BLOCKNUMBER` [required] - a hex code of an integer representing the `BLOCKNUMBER` or one of the following special params:
  
  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

    params: [
      '0xA61F98'
    ]

**Returns**

- `SIGNERS` - signers set of the block of given `BLOCKNUMBER`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}
```

<h3 id="getblocksignersbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockSignersByNumberRequest](#schemagetblocksignersbynumberrequest)|true|none|

<h3 id="getblocksignersbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockSignersByHash

<a id="opIdgetBlockSignersByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockSignersByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockSignersByHash","params":["0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockSignersByHash",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockSignersByHash',
  params: 
   [ '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockSignersByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockSignersByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockSignersByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockSignersByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")
  .asString();
```

`POST /getBlockSignersByHash`

Returns the signers set of the block of given `BLOCKHASH`.

**Parameters**

- `BLOCKHASH` [required] - a string representing a `BLOCKHASH`

    params: [
      '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'
    ]

**Returns**

- `SIGNERS` - signers set of the block of given `BLOCKHASH`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}
```

<h3 id="getblocksignersbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockSignersByHashRequest](#schemagetblocksignersbyhashrequest)|true|none|

<h3 id="getblocksignersbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockFinalityByNumber

<a id="opIdgetBlockFinalityByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockFinalityByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockFinalityByNumber","params":["0xA61F98"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockFinalityByNumber",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockFinalityByNumber',
  params: [ '0xA61F98' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockFinalityByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockFinalityByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockFinalityByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockFinalityByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")
  .asString();
```

`POST /getBlockFinalityByNumber`

Returns the the finality of the block of given BLOCKNUMBER.

**Parameters**

- `BLOCKNUMBER` [required] - a hex code of an integer representing the `BLOCKNUMBER` or one of the following special params:

  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

    params: [
      '0xA61F98'
    ]

**Returns**

- `BLOCK_FINALITY` - integer of the the finality of the block of given `BLOCKNUMBER`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}
```

<h3 id="getblockfinalitybynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockFinalityByNumberRequest](#schemagetblockfinalitybynumberrequest)|true|none|

<h3 id="getblockfinalitybynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockFinalityByHash

<a id="opIdgetBlockFinalityByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getBlockFinalityByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockFinalityByHash","params":["0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getBlockFinalityByHash",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getBlockFinalityByHash',
  params: 
   [ '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getBlockFinalityByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getBlockFinalityByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getBlockFinalityByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getBlockFinalityByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")
  .asString();
```

`POST /getBlockFinalityByHash`

Returns the the finality of the block of given `BLOCKHASH`.

**Parameters**

`BLOCKHASH` [required] - a string representing a `BLOCKHASH`

    params: [
      '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'
    ]

**Returns**

- `BLOCK_FINALITY` - integer of the the finality of the block of given `BLOCKHASH`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}
```

<h3 id="getblockfinalitybyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockFinalityByHashRequest](#schemagetblockfinalitybyhashrequest)|true|none|

<h3 id="getblockfinalitybyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCandidates

<a id="opIdgetCandidates"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getCandidates \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCandidates","params":["latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getCandidates",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getCandidates',
  params: [ 'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getCandidates"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getCandidates")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getCandidates", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getCandidates")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}")
  .asString();
```

`POST /getCandidates`

Returns the statuses of all candidates at a specific epoch

**Parameters**

  - `EPOCH_NUMBER` [required] - a hex code of an integer representing the `EPOCH_NUMBER` or the following special param:

      - `latest`: get the status of candidate at the current time

      params: [
        'latest'
      ]

**Returns**

  - `EPOCH` - the epoch number of the query of this request

  - `CANDIDATES` - list of candidates along with their statuses and capacities

      - `STATUS` - a string representing status of the corresponding candidate

      - `MASTERNODE` - if the candidate is a masternode
      
      - `SLASHED` - if the candidate is slashed

      - `PROPOSED` - if the candidate is proposed, have not been a masternode yet

      - `empty string` - if it's not a candidate

  - `CAPACITY` - capacity of the corresponding candidate

  - `SUCCESS` - true if the request is successful, otherwise it's false

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidates",
  "params": [
    "latest"
  ],
  "id": 1
}
```

<h3 id="getcandidates-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCandidatesRequest](#schemagetcandidatesrequest)|true|none|

<h3 id="getcandidates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCandidateStatus

<a id="opIdgetCandidateStatus"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getCandidateStatus \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCandidateStatus","params":["0x1d50df657b6dce50bac634bf18e2d986d807e940","latest"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getCandidateStatus",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getCandidateStatus',
  params: [ '0x1d50df657b6dce50bac634bf18e2d986d807e940', 'latest' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getCandidateStatus"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getCandidateStatus")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getCandidateStatus", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getCandidateStatus")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getCandidateStatus`

Returns the status of the candidate of given `COINBASE_ADDRESS` at a specific epoch

**Parameters**

  - `COINBASE_ADDRESS` [required] - a string representing a `COINBASE_ADDRESS` (length: 40, start with 0x )

  - `EPOCH_NUMBER` [required] - a hex code of an integer representing the `EPOCH_NUMBER` or the following special param:

      - `latest`: get the status of candidate at the current time

      params: [
        '0x1d50df657b6dce50bac634bf18e2d986d807e940',
        'latest'
      ]

  
**Returns**

  - `STATUS` - a string representing status of the candicate of given `COINBASE_ADDRESS`

      - `MASTERNODE` - if the candidate is a masternode

      - `SLASHED` - if the candidate is slashed

      - `PROPOSED` - if the candidate is proposed, have not been a masternode yet

      - `empty string` - if it's not a candidate

  - `CAPACITY` - capacity of the candidate

  - `EPOCH` - the epoch number of the query of this request

  - `SUCCESS` - true if the request is successful, otherwise it's false

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidateStatus",
  "params": [
    "0x1d50df657b6dce50bac634bf18e2d986d807e940",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getcandidatestatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCandidateStatusRequest](#schemagetcandidatestatusrequest)|true|none|

<h3 id="getcandidatestatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByHash

<a id="opIdgetTransactionByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getTransactionByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByHash","params":["0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getTransactionByHash",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getTransactionByHash',
  params: 
   [ '0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getTransactionByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getTransactionByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getTransactionByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getTransactionByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByHash`

Returns the information about a transaction requested by transaction hash.

**Parameters**

- `DATA`, 32 Bytes - hash of a transaction

    params: [
      "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
    ]

**Returns**

`Object` - A transaction object, or null when no transaction was found:

  - `hash`: `DATA`, 32 Bytes - hash of the transaction.

  - `nonce`: `QUANTITY` - the number of transactions made by the sender prior to this one.

  - `blockHash`: `DATA`, 32 Bytes - hash of the block where this transaction was in. `null` when its pending.

  - `blockNumber`: `QUANTITY` - block number where this transaction was in. `null` when its pending.

  - `transactionIndex`: `QUANTITY` - integer of the transactions index position in the block. `null` when its pending.

  - `from`: `DATA`, 20 Bytes - address of the sender.

  - `to`: `DATA`, 20 Bytes - address of the receiver. `null` when its a contract creation transaction.

  - `value`: `QUANTITY` - value transferred in Wei.

  - `gasPrice`: `QUANTITY` - gas price provided by the sender in Wei.

  - `gas`: `QUANTITY` - gas provided by the sender.

  - `input`: `DATA` - the data send along with the transaction.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByHash",
  "params": [
    "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByHashRequest](#schemagettransactionbyhashrequest)|true|none|

<h3 id="gettransactionbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByBlockHashAndIndex

<a id="opIdgetTransactionByBlockHashAndIndex"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getTransactionByBlockHashAndIndex \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByBlockHashAndIndex","params":["0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7","0x0"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getTransactionByBlockHashAndIndex",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getTransactionByBlockHashAndIndex',
  params: 
   [ '0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7',
     '0x0' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getTransactionByBlockHashAndIndex"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getTransactionByBlockHashAndIndex")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getTransactionByBlockHashAndIndex", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getTransactionByBlockHashAndIndex")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByBlockHashAndIndex`

Returns information about a transaction by block hash and transaction index position.
**Parameters**

- `DATA`, 32 Bytes - hash of a block.
- `QUANTITY` - integer of the transaction index position.

    params: [
      '0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7',
      '0x0' // 0
    ]

**Returns**
See `eth_getTransactionByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockHashAndIndex",
  "params": [
    "0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7",
    "0x0"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyblockhashandindex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByBlockHashAndIndexRequest](#schemagettransactionbyblockhashandindexrequest)|true|none|

<h3 id="gettransactionbyblockhashandindex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByBlockNumberAndIndex

<a id="opIdgetTransactionByBlockNumberAndIndex"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getTransactionByBlockNumberAndIndex \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByBlockNumberAndIndex","params":["0x52A96E","0x1"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getTransactionByBlockNumberAndIndex",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getTransactionByBlockNumberAndIndex',
  params: [ '0x52A96E', '0x1' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getTransactionByBlockNumberAndIndex"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getTransactionByBlockNumberAndIndex")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getTransactionByBlockNumberAndIndex", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getTransactionByBlockNumberAndIndex")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByBlockNumberAndIndex`

Returns information about a transaction by block number and transaction index position.

**Parameters**

- `QUANTITY|TAG` - a block number, or the string `"earliest"`, `"latest"` or `"pending"`, as in the default block parameter.
- `QUANTITY` - the transaction index position.

    params: [
      '0x29c', // 668
      '0x0' // 0
    ]

**Returns**

See `eth_getTransactionByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockNumberAndIndex",
  "params": [
    "0x52A96E",
    "0x1"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyblocknumberandindex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByBlockNumberAndIndexRequest](#schemagettransactionbyblocknumberandindexrequest)|true|none|

<h3 id="gettransactionbyblocknumberandindex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionReceipt

<a id="opIdgetTransactionReceipt"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com/getTransactionReceipt \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionReceipt","params":["0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"],"id":1}'
```

```node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "/getTransactionReceipt",
  "headers": {
    "content-type": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ jsonrpc: '2.0',
  method: 'eth_getTransactionReceipt',
  params: 
   [ '0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f' ],
  id: 1 }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://rpc.tomochain.com/getTransactionReceipt"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://rpc.tomochain.com/getTransactionReceipt")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/getTransactionReceipt", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com/getTransactionReceipt")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}")
  .asString();
```

`POST /getTransactionReceipt`

Returns the receipt of a transaction by transaction hash.

**Note:** That the receipt is not available for pending transactions.

**Parameters**

- `DATA`, 32 Bytes - hash of a transaction


**Returns**

`Object` - A transaction receipt object, or `null` when no receipt was found:

  - `transactionHash`: `DATA`, 32 Bytes - hash of the transaction.

  - `transactionIndex`: `QUANTITY` - integer of the transactions index position in the block.

  - `blockHash`: `DATA`, 32 Bytes - hash of the block where this transaction was in.

  - `blockNumber`: `QUANTITY` - block number where this transaction was in.

  - `cumulativeGasUsed`: `QUANTITY` - The total amount of gas used when this transaction was executed in the block.

  - `gasUsed`: `QUANTITY` - The amount of gas used by this specific transaction alone.

  - `contractAddress`: `DATA`, 20 Bytes - The contract address created, if the transaction was a contract creation, otherwise `null`.

  - `logs`: `Array` - Array of log objects, which this transaction generated.

  - `logsBloom`: `DATA`, 256 Bytes - Bloom filter for light clients to quickly retrieve related logs.

It also returns either :

  - `root` : `DATA` 32 bytes of post-transaction stateroot (pre Byzantium)

  - `status`: `QUANTITY` either `1` (success) or `0` (failure)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionReceipt",
  "params": [
    "0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"
  ],
  "id": 1
}
```

<h3 id="gettransactionreceipt-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionReceiptRequest](#schemagettransactionreceiptrequest)|true|none|

<h3 id="gettransactionreceipt-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_clientVersionRequest">clientVersionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaclientversionrequest"></a>
<a id="schema_clientVersionRequest"></a>
<a id="tocSclientversionrequest"></a>
<a id="tocsclientversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "web3_clientVersion",
  "params": [],
  "id": 1
}

```

clientVersionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_sha3request">sha3request</h2>
<!-- backwards compatibility -->
<a id="schemasha3request"></a>
<a id="schema_sha3request"></a>
<a id="tocSsha3request"></a>
<a id="tocssha3request"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "web3_sha3",
  "params": [
    "0x68656c6c6f20776f726c64"
  ],
  "id": 64
}

```

sha3request

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_versionrequest">versionrequest</h2>
<!-- backwards compatibility -->
<a id="schemaversionrequest"></a>
<a id="schema_versionrequest"></a>
<a id="tocSversionrequest"></a>
<a id="tocsversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_version",
  "params": [],
  "id": 67
}

```

versionrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_listeningrequest">listeningrequest</h2>
<!-- backwards compatibility -->
<a id="schemalisteningrequest"></a>
<a id="schema_listeningrequest"></a>
<a id="tocSlisteningrequest"></a>
<a id="tocslisteningrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_listening",
  "params": [],
  "id": 67
}

```

listeningrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_peerCountRequest">peerCountRequest</h2>
<!-- backwards compatibility -->
<a id="schemapeercountrequest"></a>
<a id="schema_peerCountRequest"></a>
<a id="tocSpeercountrequest"></a>
<a id="tocspeercountrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_peerCount",
  "params": [],
  "id": 74
}

```

peerCountRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_protocolVersionRequest">protocolVersionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaprotocolversionrequest"></a>
<a id="schema_protocolVersionRequest"></a>
<a id="tocSprotocolversionrequest"></a>
<a id="tocsprotocolversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_protocolVersion",
  "params": [],
  "id": 67
}

```

protocolVersionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_syncingrequest">syncingrequest</h2>
<!-- backwards compatibility -->
<a id="schemasyncingrequest"></a>
<a id="schema_syncingrequest"></a>
<a id="tocSsyncingrequest"></a>
<a id="tocssyncingrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_syncing",
  "params": [],
  "id": 1
}

```

syncingrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_coinbaserequest">coinbaserequest</h2>
<!-- backwards compatibility -->
<a id="schemacoinbaserequest"></a>
<a id="schema_coinbaserequest"></a>
<a id="tocScoinbaserequest"></a>
<a id="tocscoinbaserequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_coinbase",
  "params": [],
  "id": 64
}

```

coinbaserequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_gasPriceRequest">gasPriceRequest</h2>
<!-- backwards compatibility -->
<a id="schemagaspricerequest"></a>
<a id="schema_gasPriceRequest"></a>
<a id="tocSgaspricerequest"></a>
<a id="tocsgaspricerequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_gasPrice",
  "params": [],
  "id": 73
}

```

gasPriceRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_accountsrequest">accountsrequest</h2>
<!-- backwards compatibility -->
<a id="schemaaccountsrequest"></a>
<a id="schema_accountsrequest"></a>
<a id="tocSaccountsrequest"></a>
<a id="tocsaccountsrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_accounts",
  "params": [],
  "id": 1
}

```

accountsrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_blockNumberRequest">blockNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemablocknumberrequest"></a>
<a id="schema_blockNumberRequest"></a>
<a id="tocSblocknumberrequest"></a>
<a id="tocsblocknumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_blockNumber",
  "params": [],
  "id": 83
}

```

blockNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBalanceRequest">getBalanceRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetbalancerequest"></a>
<a id="schema_getBalanceRequest"></a>
<a id="tocSgetbalancerequest"></a>
<a id="tocsgetbalancerequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBalance",
  "params": [
    "0x2b5634c42055806a59e9107ed44d43c426e58258",
    "latest"
  ],
  "id": 1
}

```

getBalanceRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getStorageAtRequest">getStorageAtRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetstorageatrequest"></a>
<a id="schema_getStorageAtRequest"></a>
<a id="tocSgetstorageatrequest"></a>
<a id="tocsgetstorageatrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getStorageAt",
  "params": [
    "0x295a70b2de5e3953354a6a8344e616ed314d7251",
    "0x0",
    "latest"
  ],
  "id": 1
}

```

getStorageAtRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionCountRequest">getTransactionCountRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactioncountrequest"></a>
<a id="schema_getTransactionCountRequest"></a>
<a id="tocSgettransactioncountrequest"></a>
<a id="tocsgettransactioncountrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionCount",
  "params": [
    "0xbf1dcb735e512b731abd3404c15df6431bd03d42",
    "latest"
  ],
  "id": 1
}

```

getTransactionCountRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockTransactionCountByHashRequest">getBlockTransactionCountByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocktransactioncountbyhashrequest"></a>
<a id="schema_getBlockTransactionCountByHashRequest"></a>
<a id="tocSgetblocktransactioncountbyhashrequest"></a>
<a id="tocsgetblocktransactioncountbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByHash",
  "params": [
    "0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"
  ],
  "id": 1
}

```

getBlockTransactionCountByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockTransactionCountByNumberRequest">getBlockTransactionCountByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocktransactioncountbynumberrequest"></a>
<a id="schema_getBlockTransactionCountByNumberRequest"></a>
<a id="tocSgetblocktransactioncountbynumberrequest"></a>
<a id="tocsgetblocktransactioncountbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByNumber",
  "params": [
    "0x52A8CA"
  ],
  "id": 1
}

```

getBlockTransactionCountByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCodeRequest">getCodeRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcoderequest"></a>
<a id="schema_getCodeRequest"></a>
<a id="tocSgetcoderequest"></a>
<a id="tocsgetcoderequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCode",
  "params": [
    "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
    "0x2"
  ],
  "id": 1
}

```

getCodeRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_signrequest">signrequest</h2>
<!-- backwards compatibility -->
<a id="schemasignrequest"></a>
<a id="schema_signrequest"></a>
<a id="tocSsignrequest"></a>
<a id="tocssignrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sign",
  "params": [
    "0x9b2055d370f73ec7d8a03e965129118dc8f5bf83",
    "0xdeadbeaf"
  ],
  "id": 1
}

```

signrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_sendTransactionRequest">sendTransactionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasendtransactionrequest"></a>
<a id="schema_sendTransactionRequest"></a>
<a id="tocSsendtransactionrequest"></a>
<a id="tocssendtransactionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendTransaction",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}

```

sendTransactionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[[Param](#schemaparam)]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_Param">Param</h2>
<!-- backwards compatibility -->
<a id="schemaparam"></a>
<a id="schema_Param"></a>
<a id="tocSparam"></a>
<a id="tocsparam"></a>

```json
{
  "from": 1.0393608864131634e+48,
  "to": 1.2127714812045434e+48,
  "gas": 30400,
  "gasPrice": 10000000000000,
  "value": 2441406250,
  "data": 4.537516814050981e+98
}

```

Param

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|true|none|none|
|to|string|true|none|none|
|gas|string|true|none|none|
|gasPrice|string|true|none|none|
|value|string|true|none|none|
|data|string|true|none|none|

<h2 id="tocS_sendRawTransactionRequest">sendRawTransactionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasendrawtransactionrequest"></a>
<a id="schema_sendRawTransactionRequest"></a>
<a id="tocSsendrawtransactionrequest"></a>
<a id="tocssendrawtransactionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendRawTransaction",
  "params": [
    "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
  ],
  "id": 1
}

```

sendRawTransactionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_callrequest">callrequest</h2>
<!-- backwards compatibility -->
<a id="schemacallrequest"></a>
<a id="schema_callrequest"></a>
<a id="tocScallrequest"></a>
<a id="tocscallrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_call",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    },
    "latest"
  ],
  "id": 1
}

```

callrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[[Param1](#schemaparam1)]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_Param1">Param1</h2>
<!-- backwards compatibility -->
<a id="schemaparam1"></a>
<a id="schema_Param1"></a>
<a id="tocSparam1"></a>
<a id="tocsparam1"></a>

```json
{
  "from": "",
  "to": "",
  "gas": "",
  "gasPrice": "",
  "value": "",
  "data": ""
}

```

Param1

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|false|none|none|
|to|string|false|none|none|
|gas|string|false|none|none|
|gasPrice|string|false|none|none|
|value|string|false|none|none|
|data|string|false|none|none|

<h2 id="tocS_estimateGasRequest">estimateGasRequest</h2>
<!-- backwards compatibility -->
<a id="schemaestimategasrequest"></a>
<a id="schema_estimateGasRequest"></a>
<a id="tocSestimategasrequest"></a>
<a id="tocsestimategasrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_estimateGas",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}

```

estimateGasRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockByHashRequest">getBlockByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockbyhashrequest"></a>
<a id="schema_getBlockByHashRequest"></a>
<a id="tocSgetblockbyhashrequest"></a>
<a id="tocsgetblockbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByHash",
  "params": [
    "0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",
    true
  ],
  "id": 1
}

```

getBlockByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockByNumberRequest">getBlockByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockbynumberrequest"></a>
<a id="schema_getBlockByNumberRequest"></a>
<a id="tocSgetblockbynumberrequest"></a>
<a id="tocsgetblockbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": [
    "0x0",
    true
  ],
  "id": 1
}

```

getBlockByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockSignersByNumberRequest">getBlockSignersByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocksignersbynumberrequest"></a>
<a id="schema_getBlockSignersByNumberRequest"></a>
<a id="tocSgetblocksignersbynumberrequest"></a>
<a id="tocsgetblocksignersbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}

```

getBlockSignersByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockSignersByHashRequest">getBlockSignersByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocksignersbyhashrequest"></a>
<a id="schema_getBlockSignersByHashRequest"></a>
<a id="tocSgetblocksignersbyhashrequest"></a>
<a id="tocsgetblocksignersbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}

```

getBlockSignersByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockFinalityByNumberRequest">getBlockFinalityByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockfinalitybynumberrequest"></a>
<a id="schema_getBlockFinalityByNumberRequest"></a>
<a id="tocSgetblockfinalitybynumberrequest"></a>
<a id="tocsgetblockfinalitybynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}

```

getBlockFinalityByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockFinalityByHashRequest">getBlockFinalityByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockfinalitybyhashrequest"></a>
<a id="schema_getBlockFinalityByHashRequest"></a>
<a id="tocSgetblockfinalitybyhashrequest"></a>
<a id="tocsgetblockfinalitybyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}

```

getBlockFinalityByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByHashRequest">getTransactionByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyhashrequest"></a>
<a id="schema_getTransactionByHashRequest"></a>
<a id="tocSgettransactionbyhashrequest"></a>
<a id="tocsgettransactionbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByHash",
  "params": [
    "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
  ],
  "id": 1
}

```

getTransactionByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByBlockHashAndIndexRequest">getTransactionByBlockHashAndIndexRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyblockhashandindexrequest"></a>
<a id="schema_getTransactionByBlockHashAndIndexRequest"></a>
<a id="tocSgettransactionbyblockhashandindexrequest"></a>
<a id="tocsgettransactionbyblockhashandindexrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockHashAndIndex",
  "params": [
    "0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7",
    "0x0"
  ],
  "id": 1
}

```

getTransactionByBlockHashAndIndexRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByBlockNumberAndIndexRequest">getTransactionByBlockNumberAndIndexRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyblocknumberandindexrequest"></a>
<a id="schema_getTransactionByBlockNumberAndIndexRequest"></a>
<a id="tocSgettransactionbyblocknumberandindexrequest"></a>
<a id="tocsgettransactionbyblocknumberandindexrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockNumberAndIndex",
  "params": [
    "0x52A96E",
    "0x1"
  ],
  "id": 1
}

```

getTransactionByBlockNumberAndIndexRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionReceiptRequest">getTransactionReceiptRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionreceiptrequest"></a>
<a id="schema_getTransactionReceiptRequest"></a>
<a id="tocSgettransactionreceiptrequest"></a>
<a id="tocsgettransactionreceiptrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionReceipt",
  "params": [
    "0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"
  ],
  "id": 1
}

```

getTransactionReceiptRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCandidatesRequest">getCandidatesRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcandidatesrequest"></a>
<a id="schema_getCandidatesRequest"></a>
<a id="tocSgetcandidatesrequest"></a>
<a id="tocsgetcandidatesrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidates",
  "params": [
    "latest"
  ],
  "id": 1
}

```

getCandidateStatusRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCandidateStatusRequest">getCandidateStatusRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcandidatestatusrequest"></a>
<a id="schema_getCandidateStatusRequest"></a>
<a id="tocSgetcandidatestatusrequest"></a>
<a id="tocsgetcandidatestatusrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidateStatus",
  "params": [
    "0x1d50df657b6dce50bac634bf18e2d986d807e940",
    "latest"
  ],
  "id": 1
}

```

getCandidateStatusRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|


<h1 id="tomodex-apis">TomoDex APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

TomoDex API Document

Base Url: https://dex.testnet.tomochain.com/api (testnet)

<h1 id="tomodex-apis-accounts">accounts</h1>

Account endpoints

## Find account by user address

<a id="opIdhandleGetAccount"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account/{userAddress} \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/account/{userAddress}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account/{userAddress}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/account/{userAddress}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/account/{userAddress}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/{userAddress}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /account/{userAddress}`

Returns a single account

<h3 id="find-account-by-user-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|path|string|true|Address of user to return|

> Example responses

> 200 Response

```json
{
  "address": "0xF7349C253FF7747Df661296E0859c44e974fb52E"
}
```

<h3 id="find-account-by-user-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Account](#schemaaccount)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## [Deprecated] Find account's token balance by user address and token address

<a id="opIdhandleGetAccountTokenBalance"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account/{userAddress}/{tokenAddress} \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/account/{userAddress}/{tokenAddress}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account/{userAddress}/{tokenAddress}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/account/{userAddress}/{tokenAddress}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/account/{userAddress}/{tokenAddress}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/{userAddress}/{tokenAddress}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /account/{userAddress}/{tokenAddress}`

Returns an object contains token balance of user

<h3 id="[deprecated]-find-account's-token-balance-by-user-address-and-token-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|path|string|true|Address of user to find token balance|
|tokenAddress|path|string|true|Address of token|

> Example responses

> 200 Response

```json
{
  "address": "string",
  "symbol": "string",
  "balance": "string",
  "availableBalance": "string",
  "inOrderBalance": "string"
}
```

<h3 id="[deprecated]-find-account's-token-balance-by-user-address-and-token-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[TokenBalance](#schematokenbalance)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Add a new account by user address

<a id="opIdhandleCreateAccount"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /account/create \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/account/create',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/account/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post '/account/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/account/create', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /account/create`

Returns newly created account

<h3 id="add-a-new-account-by-user-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|newAddress|path|string|true|Address of user|

> Example responses

> 201 Response

```json
{
  "address": "0xF7349C253FF7747Df661296E0859c44e974fb52E"
}
```

<h3 id="add-a-new-account-by-user-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Account already exists|None|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Account created|[Account](#schemaaccount)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Invalid Address|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-tokens">tokens</h1>

Token endpoints

## Finds all tokens

<a id="opIdHandleGetTokens"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /tokens \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/tokens',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/tokens", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/tokens',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/tokens', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/tokens");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /tokens`

Return all tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="finds-all-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new token

<a id="opIdHandleCreateToken"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /tokens \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "active": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/tokens',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/tokens", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/tokens',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/tokens', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/tokens");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /tokens`

Returns newly created token

> Body parameter

```json
{
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "active": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string"
}
```

<h3 id="create-new-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Token](#schematoken)|true|Token object that needs to be added|
|» id|body|string|false|none|
|» name|body|string|false|none|
|» symbol|body|string|false|none|
|» address|body|string|false|none|
|» image|body|[Image](#schemaimage)|false|none|
|»» url|body|string|false|none|
|»» meta|body|object|false|none|
|» contractAddress|body|string|false|none|
|» decimals|body|integer(int32)|false|none|
|» active|body|boolean|false|none|
|» listed|body|boolean|false|none|
|» quote|body|boolean|false|none|
|» makeFee|body|string|false|none|
|» takeFee|body|string|false|none|
|» usd|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="create-new-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Token](#schematoken)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Finds all base tokens

<a id="opIdHandleGetBaseTokens"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /tokens/base \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/tokens/base',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/tokens/base", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/tokens/base',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/tokens/base', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/tokens/base");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /tokens/base`

Return all base tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="finds-all-base-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-base-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Finds all quote tokens

<a id="opIdHandleGetQuoteTokens"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /tokens/quote \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/tokens/quote',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/tokens/quote", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/tokens/quote',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/tokens/quote', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/tokens/quote");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /tokens/quote`

Return all quote tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="finds-all-quote-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-quote-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the token information corresponding to an address

<a id="opIdHandleGetToken"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /tokens/{address} \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/tokens/{address}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/tokens/{address}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/tokens/{address}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/tokens/{address}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/tokens/{address}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /tokens/{address}`

Return token object

<h3 id="retrieve-the-token-information-corresponding-to-an-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|string|true|Token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="retrieve-the-token-information-corresponding-to-an-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Token](#schematoken)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-pairs">pairs</h1>

Pair endpoints

## Finds all pairs

<a id="opIdHandleGetPairs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /pairs?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/pairs?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/pairs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/pairs',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/pairs', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/pairs?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /pairs`

Return all pairs in an array

<h3 id="finds-all-pairs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "baseTokenSymbol": "string",
    "baseTokenAddress": "string",
    "baseTokenDecimals": 0,
    "quoteTokenSymbol": "string",
    "quoteTokenAddress": "string",
    "quoteTokenDecimals": 0,
    "listed": true,
    "active": true,
    "rank": 0,
    "makeFee": "string",
    "takeFee": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="finds-all-pairs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-pairs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pair](#schemapair)]|false|none|none|
|» id|string|false|read-only|none|
|» baseTokenSymbol|string|false|none|none|
|» baseTokenAddress|string|false|none|none|
|» baseTokenDecimals|integer(int32)|false|read-only|none|
|» quoteTokenSymbol|string|false|none|none|
|» quoteTokenAddress|string|false|none|none|
|» quoteTokenDecimals|integer(int32)|false|read-only|none|
|» listed|boolean|false|read-only|none|
|» active|boolean|false|none|none|
|» rank|integer(int32)|false|read-only|none|
|» makeFee|string|false|read-only|none|
|» takeFee|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new pair

<a id="opIdHandleCreatePair"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /pairs \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "active": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/pairs',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/pairs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/pairs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/pairs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/pairs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /pairs`

Returns newly created pair

> Body parameter

```json
{
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "active": true
}
```

<h3 id="create-new-pair-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pair](#schemapair)|true|Pair object that needs to be added|
|» id|body|string|false|none|
|» baseTokenSymbol|body|string|false|none|
|» baseTokenAddress|body|string|false|none|
|» baseTokenDecimals|body|integer(int32)|false|none|
|» quoteTokenSymbol|body|string|false|none|
|» quoteTokenAddress|body|string|false|none|
|» quoteTokenDecimals|body|integer(int32)|false|none|
|» listed|body|boolean|false|none|
|» active|body|boolean|false|none|
|» rank|body|integer(int32)|false|none|
|» makeFee|body|string|false|none|
|» takeFee|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="create-new-pair-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the pair information corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetPair"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /pair?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/pair?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/pair", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/pair',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/pair', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/pair?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /pair`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-pair-information-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="retrieve-the-pair-information-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve pair data corresponding to a baseToken and quoteToken

<a id="opIdHandleGetPairData"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /pair/data?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/pair/data?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/pair/data", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/pair/data',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/pair/data', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/pair/data?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /pair/data`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-pair-data-corresponding-to-a-basetoken-and-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "averageOrderAmount": "string",
  "averageTradeAmount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-pair-data-corresponding-to-a-basetoken-and-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all pair data

<a id="opIdHandleGetPairsData"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /pairs/data \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/pairs/data',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/pairs/data", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/pairs/data',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/pairs/data', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/pairs/data");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /pairs/data`

Multiple status values can be provided with comma separated strings

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "averageOrderAmount": "string",
  "averageTradeAmount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-all-pair-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-orders">orders</h1>

Order endpoints

## Retrieve the sorted list of orders for an Ethereum address

<a id="opIdhandleGetOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orders \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orders', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orders`

Return all orders in an array

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|false|User address|
|pageOffset|query|string|false|Page offset|
|pageSize|query|string|false|Number of items per a page|
|sortBy|query|string|false|Sort for query (time, orderStatus, orderType, orderSide)|
|sortType|query|string|false|asc/dec|
|orderStatus|query|string|false|OPEN/CANCELLED/FILLED/PARTIAL_FILLED|
|orderSide|query|string|false|SELL/BUY|
|orderType|query|string|false|LO/MO|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}
```

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» orders|[[Order](#schemaorder)]|false|none|none|
|»» id|string|false|read-only|none|
|»» userAddress|string|false|none|none|
|»» exchangeAddress|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» status|string|false|none|none|
|»» side|string|false|none|none|
|»» type|string|false|none|none|
|»» hash|string|false|none|none|
|»» signature|[Signature](#schemasignature)|false|none|none|
|»»» V|string|false|none|none|
|»»» R|string|false|none|none|
|»»» S|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» filledAmount|string|false|none|none|
|»» nonce|string|false|none|none|
|»» makeFee|string|false|none|none|
|»» takeFee|string|false|none|none|
|»» pairName|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new order

<a id="opIdHandleNewOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "userAddress": "0x15e08dE16f534c890828F2a0D935433aF5B3CE0C",
  "exchangeAddress": "0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e",
  "baseToken": "0x4d7eA2cE949216D6b120f3AA10164173615A2b6C",
  "quoteToken": "0x0000000000000000000000000000000000000001",
  "side": "SELL/BUY",
  "type": "LO/MO",
  "status": "NEW/CANCELLED",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "21207020000000000000000",
  "amount": "4693386710283129",
  "nonce": "1",
  "makeFee": "1",
  "takeFee": "1"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/orders',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/orders', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /orders`

Returns newly created order

> Body parameter

```json
{
  "userAddress": "0x15e08dE16f534c890828F2a0D935433aF5B3CE0C",
  "exchangeAddress": "0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e",
  "baseToken": "0x4d7eA2cE949216D6b120f3AA10164173615A2b6C",
  "quoteToken": "0x0000000000000000000000000000000000000001",
  "side": "SELL/BUY",
  "type": "LO/MO",
  "status": "NEW/CANCELLED",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "21207020000000000000000",
  "amount": "4693386710283129",
  "nonce": "1",
  "makeFee": "1",
  "takeFee": "1"
}
```

<h3 id="create-new-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCreate](#schemaordercreate)|true|Order object that needs to be added|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "userAddress": "string",
  "exchangeAddress": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "status": "string",
  "side": "string",
  "type": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "string",
  "amount": "string",
  "filledAmount": "string",
  "nonce": "string",
  "makeFee": "string",
  "takeFee": "string",
  "pairName": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="create-new-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Account is blocked|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## [Deprecated] Retrieve the list of positions for an Ethereum address. Positions are order that have been sent to the matching engine and that are waiting to be matched

<a id="opIdhandleGetPositions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orders/positions?address=string&limit=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders/positions?address=string&limit=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orders/positions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orders/positions',
  params: {
  'address' => 'string',
'limit' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orders/positions', params={
  'address': 'string',  'limit': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/positions?address=string&limit=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orders/positions`

Return all orders in an array

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|limit|query|string|true|Number of orders returned in query|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "userAddress": "string",
    "exchangeAddress": "string",
    "baseToken": "string",
    "quoteToken": "string",
    "status": "string",
    "side": "string",
    "type": "string",
    "hash": "string",
    "signature": {
      "V": "string",
      "R": "string",
      "S": "string"
    },
    "pricepoint": "string",
    "amount": "string",
    "filledAmount": "string",
    "nonce": "string",
    "makeFee": "string",
    "takeFee": "string",
    "pairName": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Order](#schemaorder)]|false|none|none|
|» id|string|false|read-only|none|
|» userAddress|string|false|none|none|
|» exchangeAddress|string|false|none|none|
|» baseToken|string|false|none|none|
|» quoteToken|string|false|none|none|
|» status|string|false|none|none|
|» side|string|false|none|none|
|» type|string|false|none|none|
|» hash|string|false|none|none|
|» signature|[Signature](#schemasignature)|false|none|none|
|»» V|string|false|none|none|
|»» R|string|false|none|none|
|»» S|string|false|none|none|
|» pricepoint|string|false|none|none|
|» amount|string|false|none|none|
|» filledAmount|string|false|none|none|
|» nonce|string|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» pairName|string|false|none|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the list of filled order for an Ethereum address

<a id="opIdhandleGetOrderHistory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orders/history?address=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders/history?address=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orders/history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orders/history',
  params: {
  'address' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orders/history', params={
  'address': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/history?address=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orders/history`

Return all orders in an array

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|pageOffset|query|string|false|Page offset, default 0|
|pageSize|query|string|false|Number of items per a page, defaul 50|
|sortBy|query|string|false|Sort for query (time(default), orderStatus, orderType, orderSide)|
|sortType|query|string|false|asc/dec, default asc|
|orderStatus|query|string|false|OPEN/CANCELLED/FILLED/PARTIAL_FILLED|
|orderSide|query|string|false|SELL/BUY|
|orderType|query|string|false|LO/MO|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}
```

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» orders|[[Order](#schemaorder)]|false|none|none|
|»» id|string|false|read-only|none|
|»» userAddress|string|false|none|none|
|»» exchangeAddress|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» status|string|false|none|none|
|»» side|string|false|none|none|
|»» type|string|false|none|none|
|»» hash|string|false|none|none|
|»» signature|[Signature](#schemasignature)|false|none|none|
|»»» V|string|false|none|none|
|»»» R|string|false|none|none|
|»»» S|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» filledAmount|string|false|none|none|
|»» nonce|string|false|none|none|
|»» makeFee|string|false|none|none|
|»» takeFee|string|false|none|none|
|»» pairName|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the total number of orders for an Ethereum address

<a id="opIdhandleGetCountOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orders/count?address=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders/count?address=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orders/count", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orders/count',
  params: {
  'address' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orders/count', params={
  'address': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/count?address=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orders/count`

Return a positive integer

<h3 id="retrieve-the-total-number-of-orders-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
0
```

<h3 id="retrieve-the-total-number-of-orders-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|integer|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve order nonce for an Ethereum address

<a id="opIdhandleGetOrderNonce"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orders/nonce?address=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders/nonce?address=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orders/nonce", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orders/nonce',
  params: {
  'address' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orders/nonce', params={
  'address': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/nonce?address=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orders/nonce`

Return a positive integer

<h3 id="retrieve-order-nonce-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
0
```

<h3 id="retrieve-order-nonce-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|integer|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Cancel order

<a id="opIdHandleCancelOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /orders/cancel \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "orderHash": "string",
  "nonce": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/orders/cancel',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/orders/cancel", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/orders/cancel',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/orders/cancel', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/cancel");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /orders/cancel`

Returns the hash of cancelled order

> Body parameter

```json
{
  "orderHash": "string",
  "nonce": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  }
}
```

<h3 id="cancel-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCancel](#schemaordercancel)|true|Cancel order object|
|» orderHash|body|string|false|none|
|» nonce|body|string|false|none|
|» hash|body|string|false|none|
|» signature|body|[Signature](#schemasignature)|false|none|
|»» V|body|string|false|none|
|»» R|body|string|false|none|
|»» S|body|string|false|none|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="cancel-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## [Deprecated] Cancel all orders

<a id="opIdhandleCancelAllOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /orders/cancelAll?address=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orders/cancelAll?address=string',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/orders/cancelAll", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post '/orders/cancelAll',
  params: {
  'address' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/orders/cancelAll', params={
  'address': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orders/cancelAll?address=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
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

```

`POST /orders/cancelAll`

This endpoint should implements signature authentication

<h3 id="[deprecated]-cancel-all-orders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="[deprecated]-cancel-all-orders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-orderbook">orderbook</h1>

Order book endpoints

## Retrieve the orderbook (amount and pricepoint) corresponding to a a baseToken and a quoteToken

<a id="opIdHandleGetOrderBook"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orderbook?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orderbook?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orderbook", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orderbook',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orderbook', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orderbook?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orderbook`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pairName": "string",
  "asks": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ],
  "bids": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ]
}
```

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderBook](#schemaorderbook)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the orderbook (full raw orders, including fields such as hashes, maker, taker addresses, signatures, etc.)
corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetRawOrderBook"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /orderbook/raw?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/orderbook/raw?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/orderbook/raw", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/orderbook/raw',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/orderbook/raw', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/orderbook/raw?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /orderbook/raw`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-orderbook-(full-raw-orders,-including-fields-such-as-hashes,-maker,-taker-addresses,-signatures,-etc.)
corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pairName": "string",
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}
```

<h3 id="retrieve-the-orderbook-(full-raw-orders,-including-fields-such-as-hashes,-maker,-taker-addresses,-signatures,-etc.)
corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[RawOrderBook](#schemaraworderbook)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-trades">trades</h1>

Trade endpoints

## Retrieve all trades corresponding to a baseToken or/and a quoteToken

<a id="opIdHandleGetTrades"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /trades \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/trades',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/trades", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/trades',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/trades', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/trades");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /trades`

Return all trades in an array with total match

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|pageOffset|query|string|false|none|
|pageSize|query|string|false|number of trade item per page, default 50|
|sortBy|query|string|false|Sort for query (suported sort by time)|
|sortType|query|string|false|asc/dec|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "trades": [
    {
      "id": "string",
      "taker": "string",
      "maker": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "makerOrderHash": "string",
      "takerOrderHash": "string",
      "hash": "string",
      "txHash": "string",
      "pairName": "string",
      "pricepoint": "string",
      "amount": "string",
      "status": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}
```

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» trades|[[Trade](#schematrade)]|false|none|none|
|»» id|string|false|read-only|none|
|»» taker|string|false|none|none|
|»» maker|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» makerOrderHash|string|false|none|none|
|»» takerOrderHash|string|false|none|none|
|»» hash|string|false|none|none|
|»» txHash|string|false|none|none|
|»» pairName|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» status|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the sorted list of trades for an Ethereum address in which the given address is either maker or taker

<a id="opIdHandleGetTradesHistory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /trades/history?address=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/trades/history?address=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/trades/history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/trades/history',
  params: {
  'address' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/trades/history', params={
  'address': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/trades/history?address=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /trades/history`

Return trades array

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|pageOffset|query|string|false|none|
|pageSize|query|string|false|number of trade item per page, default 50|
|sortBy|query|string|false|Sort for query (suported sort by time)|
|sortType|query|string|false|asc/dec|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "trades": [
    {
      "id": "string",
      "taker": "string",
      "maker": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "makerOrderHash": "string",
      "takerOrderHash": "string",
      "hash": "string",
      "txHash": "string",
      "pairName": "string",
      "pricepoint": "string",
      "amount": "string",
      "status": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}
```

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» trades|[[Trade](#schematrade)]|false|none|none|
|»» id|string|false|read-only|none|
|»» taker|string|false|none|none|
|»» maker|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» makerOrderHash|string|false|none|none|
|»» takerOrderHash|string|false|none|none|
|»» hash|string|false|none|none|
|»» txHash|string|false|none|none|
|»» pairName|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» status|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-ohlcv">ohlcv</h1>

OHLCV endpoints

## Retrieve OHLCV data corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetOHLCV"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/ohlcv", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/ohlcv',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string',
'timeInterval' => 'string',
'from' => 'string',
'to' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/ohlcv', params={
  'baseToken': 'string',  'quoteToken': 'string',  'timeInterval': 'string',  'from': 'string',  'to': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /ohlcv`

Return all ticks in an array

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|
|timeInterval|query|string|true|Time interval, candle size. Valid values: 1m, 3m, 5m, 15m, 30m, 1h, 2h, 4h, 6h, 8h, 12h, 1d, 1w, 1mo (1 month)|
|from|query|string|true|the beginning timestamp (number of seconds from 1970/01/01) from which ohlcv data has to be queried|
|to|query|string|true|the ending timestamp ((number of seconds from 1970/01/01)) until which ohlcv data has to be queried|

> Example responses

> 200 Response

```json
[
  {
    "pair": {
      "pairName": "string",
      "baseToken": "string",
      "quoteToken": "string"
    },
    "open": "string",
    "high": "string",
    "low": 0,
    "close": "string",
    "volume": "string",
    "count": "string",
    "timestamp": "string"
  }
]
```

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Tick](#schematick)]|false|none|none|
|» pair|[PairID](#schemapairid)|false|none|none|
|»» pairName|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|» open|string|false|none|none|
|» high|string|false|none|none|
|» low|integer(int32)|false|none|none|
|» close|string|false|none|none|
|» volume|string|false|none|none|
|» count|string|false|none|none|
|» timestamp|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-notifications">notifications</h1>

Notification endpoints

## Retrieve the list of notifications for an address with pagination

<a id="opIdHandleGetNotifications"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /notifications?userAddress=string&page=string&perPage=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/notifications?userAddress=string&page=string&perPage=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/notifications", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/notifications',
  params: {
  'userAddress' => 'string',
'page' => 'string',
'perPage' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/notifications', params={
  'userAddress': 'string',  'page': 'string',  'perPage': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/notifications?userAddress=string&page=string&perPage=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /notifications`

Return notifications in an array

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|query|string|true|User address|
|page|query|string|true|Page number|
|perPage|query|string|true|the number of records returned per page. Valid values are 10, 20, 30, 40, 50|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "recipient": "string",
    "message": "string",
    "type": "string",
    "status": "string",
    "createdAt": "2019-11-03T16:33:00Z",
    "updatedAt": "2019-11-03T16:33:00Z"
  }
]
```

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid user address|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Notification](#schemanotification)]|false|none|none|
|» id|string|false|read-only|none|
|» recipient|string|false|none|none|
|» message|string|false|none|none|
|» type|string|false|none|none|
|» status|string|false|none|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Update status of a notification from UNREAD to READ

<a id="opIdHandleNewOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /notifications/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/notifications/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/notifications/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put '/notifications/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/notifications/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/notifications/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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

```

`PUT /notifications/{id}`

Returns newly updated notification

> Body parameter

```json
{
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string"
}
```

<h3 id="update-status-of-a-notification-from-unread-to-read-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Notification](#schemanotification)|true|Notification object that needs to be updated|
|» id|body|string|false|none|
|» recipient|body|string|false|none|
|» message|body|string|false|none|
|» type|body|string|false|none|
|» status|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="update-status-of-a-notification-from-unread-to-read-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Notification](#schemanotification)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-info">info</h1>

Info endpoints

## get__info

> Code samples

```shell
# You can also use wget
curl -X GET /info \
  -H 'Accept: */*'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('/info',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/info", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/info',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/info', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/info");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /info`

> Example responses

> 200 Response

<h3 id="get__info-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="get__info-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» exchangeAddress|string|false|none|none|
|» fee|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__info_exchange

> Code samples

```shell
# You can also use wget
curl -X GET /info/exchange \
  -H 'Accept: */*'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('/info/exchange',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/info/exchange", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/info/exchange',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/info/exchange', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/info/exchange");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /info/exchange`

> Example responses

> 200 Response

<h3 id="get__info_exchange-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="get__info_exchange-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» exchangeAddress|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__info_fees

> Code samples

```shell
# You can also use wget
curl -X GET /info/fees \
  -H 'Accept: */*'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('/info/fees',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/info/fees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get '/info/fees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('/info/fees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/info/fees");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /info/fees`

> Example responses

> 200 Response

<h3 id="get__info_fees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="get__info_fees-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» fee|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-market">market</h1>

## Retrieve market stats 24h corresponding to a baseToken and a quoteToken

> Code samples

```shell
# You can also use wget
curl -X GET /market/stats?baseToken=string&quoteToken=string \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/market/stats?baseToken=string&quoteToken=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/market/stats", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/market/stats',
  params: {
  'baseToken' => 'string',
'quoteToken' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/market/stats', params={
  'baseToken': 'string',  'quoteToken': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/market/stats?baseToken=string&quoteToken=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /market/stats`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-market-stats-24h-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}
```

<h3 id="retrieve-market-stats-24h-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all market stats 2

> Code samples

```shell
# You can also use wget
curl -X GET /market/stats/all \
  -H 'Accept: application/json'

```

```nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/market/stats/all',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/market/stats/all", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/market/stats/all',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/market/stats/all', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/market/stats/all");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
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

```

`GET /market/stats/all`

Multiple status values can be provided with comma separated strings

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "averageOrderAmount": "string",
  "averageTradeAmount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-all-market-stats-2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSaccount">Account</h2>

<a id="schemaaccount"></a>

```json
{
  "address": "0xF7349C253FF7747Df661296E0859c44e974fb52E"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|address|string|false|none|none|
|tokenBalances|object|false|none|none|
|» address|string|false|none|none|
|» symbol|string|false|none|none|
|» balance|string|false|none|none|
|» availableBalance|string|false|none|none|
|» inOrderBalance|string|false|none|none|
|isBlocked|boolean|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocStokenbalance">TokenBalance</h2>

<a id="schematokenbalance"></a>

```json
{
  "address": "string",
  "symbol": "string",
  "balance": "string",
  "availableBalance": "string",
  "inOrderBalance": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address|string|false|none|none|
|symbol|string|false|none|none|
|balance|string|false|none|none|
|availableBalance|string|false|none|none|
|inOrderBalance|string|false|none|none|

<h2 id="tocStoken">Token</h2>

<a id="schematoken"></a>

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|name|string|false|none|none|
|symbol|string|false|none|none|
|address|string|false|none|none|
|image|[Image](#schemaimage)|false|none|none|
|contractAddress|string|false|none|none|
|decimals|integer(int32)|false|read-only|none|
|active|boolean|false|none|none|
|listed|boolean|false|read-only|none|
|quote|boolean|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|
|usd|string|false|read-only|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocSpair">Pair</h2>

<a id="schemapair"></a>

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|baseTokenSymbol|string|false|none|none|
|baseTokenAddress|string|false|none|none|
|baseTokenDecimals|integer(int32)|false|read-only|none|
|quoteTokenSymbol|string|false|none|none|
|quoteTokenAddress|string|false|none|none|
|quoteTokenDecimals|integer(int32)|false|read-only|none|
|listed|boolean|false|read-only|none|
|active|boolean|false|none|none|
|rank|integer(int32)|false|read-only|none|
|makeFee|string|false|read-only|none|
|takeFee|string|false|read-only|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocSpairid">PairID</h2>

<a id="schemapairid"></a>

```json
{
  "pairName": "string",
  "baseToken": "string",
  "quoteToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|

<h2 id="tocSpairdata">PairData</h2>

<a id="schemapairdata"></a>

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "averageOrderAmount": "string",
  "averageTradeAmount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pair|[PairID](#schemapairid)|false|none|none|
|open|string|false|none|none|
|high|string|false|none|none|
|low|integer(int32)|false|none|none|
|close|string|false|none|none|
|volume|string|false|none|none|
|count|string|false|none|none|
|timestamp|string|false|none|none|
|orderVolume|string|false|none|none|
|orderCount|string|false|none|none|
|averageOrderAmount|string|false|none|none|
|averageTradeAmount|string|false|none|none|
|askPrice|string|false|none|none|
|bidPrice|string|false|none|none|
|price|string|false|none|none|
|rank|integer(int32)|false|none|none|

<h2 id="tocSimage">Image</h2>

<a id="schemaimage"></a>

```json
{
  "url": "string",
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|
|meta|object|false|none|none|

<h2 id="tocSorder">Order</h2>

<a id="schemaorder"></a>

```json
{
  "id": "string",
  "userAddress": "string",
  "exchangeAddress": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "status": "string",
  "side": "string",
  "type": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "string",
  "amount": "string",
  "filledAmount": "string",
  "nonce": "string",
  "makeFee": "string",
  "takeFee": "string",
  "pairName": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|userAddress|string|false|none|none|
|exchangeAddress|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|status|string|false|none|none|
|side|string|false|none|none|
|type|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|filledAmount|string|false|none|none|
|nonce|string|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|
|pairName|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocSordercreate">OrderCreate</h2>

<a id="schemaordercreate"></a>

```json
{
  "userAddress": "0x15e08dE16f534c890828F2a0D935433aF5B3CE0C",
  "exchangeAddress": "0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e",
  "baseToken": "0x4d7eA2cE949216D6b120f3AA10164173615A2b6C",
  "quoteToken": "0x0000000000000000000000000000000000000001",
  "side": "SELL/BUY",
  "type": "LO/MO",
  "status": "NEW/CANCELLED",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "21207020000000000000000",
  "amount": "4693386710283129",
  "nonce": "1",
  "makeFee": "1",
  "takeFee": "1"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userAddress|string|false|none|none|
|exchangeAddress|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|side|string|false|none|none|
|type|string|false|none|none|
|status|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|nonce|string|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|

<h2 id="tocSordercancel">OrderCancel</h2>

<a id="schemaordercancel"></a>

```json
{
  "orderHash": "string",
  "nonce": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderHash|string|false|none|none|
|nonce|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|

<h2 id="tocSsignature">Signature</h2>

<a id="schemasignature"></a>

```json
{
  "V": "string",
  "R": "string",
  "S": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|V|string|false|none|none|
|R|string|false|none|none|
|S|string|false|none|none|

<h2 id="tocSorderbook">OrderBook</h2>

<a id="schemaorderbook"></a>

```json
{
  "pairName": "string",
  "asks": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ],
  "bids": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|asks|[object]|false|none|none|
|» amount|string|false|none|none|
|» pricepoint|string|false|none|none|
|bids|[object]|false|none|none|
|» amount|string|false|none|none|
|» pricepoint|string|false|none|none|

<h2 id="tocSraworderbook">RawOrderBook</h2>

<a id="schemaraworderbook"></a>

```json
{
  "pairName": "string",
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2019-11-03T16:33:00Z",
      "updatedAt": "2019-11-03T16:33:00Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|orders|[[Order](#schemaorder)]|false|none|none|

<h2 id="tocStrade">Trade</h2>

<a id="schematrade"></a>

```json
{
  "id": "string",
  "taker": "string",
  "maker": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "makerOrderHash": "string",
  "takerOrderHash": "string",
  "hash": "string",
  "txHash": "string",
  "pairName": "string",
  "pricepoint": "string",
  "amount": "string",
  "status": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|taker|string|false|none|none|
|maker|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|makerOrderHash|string|false|none|none|
|takerOrderHash|string|false|none|none|
|hash|string|false|none|none|
|txHash|string|false|none|none|
|pairName|string|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|status|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocStick">Tick</h2>

<a id="schematick"></a>

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pair|[PairID](#schemapairid)|false|none|none|
|open|string|false|none|none|
|high|string|false|none|none|
|low|integer(int32)|false|none|none|
|close|string|false|none|none|
|volume|string|false|none|none|
|count|string|false|none|none|
|timestamp|string|false|none|none|

<h2 id="tocSnotification">Notification</h2>

<a id="schemanotification"></a>

```json
{
  "id": "string",
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string",
  "createdAt": "2019-11-03T16:33:00Z",
  "updatedAt": "2019-11-03T16:33:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|recipient|string|false|none|none|
|message|string|false|none|none|
|type|string|false|none|none|
|status|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocSapiresponse">ApiResponse</h2>

<a id="schemaapiresponse"></a>

```json
{
  "code": 0,
  "type": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|false|none|none|
|type|string|false|none|none|
|message|string|false|none|none|



<h1 id="tomoscan-apis">TomoScan APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

TomoScan APIs

License: <a href="https://github.com/tomochain/tomoscan">Github</a>

Base URL: https://scan.tomochain.com

Swagger API Document: [https://scan.tomochain.com/docs/](https://scan.tomochain.com/docs/)

<h1 id="tomoscan-apis-accounts">Accounts</h1>

Accounts API

## Get list accounts

> Code samples

```shell
# You can also use wget
curl -X GET /api/accounts

```

```javascript
const fetch = require('node-fetch');

fetch('/api/accounts',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/accounts',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/accounts', params={

)

print r.json()

```

`GET /api/accounts`

<h3 id="get-list-accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get account detail

> Code samples

```shell
# You can also use wget
curl -X GET /api/accounts/{hash}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/accounts/{hash}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/accounts/{hash}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/accounts/{hash}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/accounts/{hash}', params={

)

print r.json()

```

`GET /api/accounts/{hash}`

<h3 id="get-account-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|account address|

<h3 id="get-account-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list block create

> Code samples

```shell
# You can also use wget
curl -X GET /api/accounts/{hash}/mined

```

```javascript
const fetch = require('node-fetch');

fetch('/api/accounts/{hash}/mined',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/accounts/{hash}/mined", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/accounts/{hash}/mined',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/accounts/{hash}/mined', params={

)

print r.json()

```

`GET /api/accounts/{hash}/mined`

<h3 id="get-list-block-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-block-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list token transactions. Require 1 of 2 conditions - address | token

> Code samples

```shell
# You can also use wget
curl -X GET /api/token-txs

```

```javascript
const fetch = require('node-fetch');

fetch('/api/token-txs',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/token-txs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/token-txs',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/token-txs', params={

)

print r.json()

```

`GET /api/token-txs`

<h3 id="get-list-token-transactions.-require-1-of-2-conditions---address-|-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|false|account address|
|token|path|string|true|token address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-token-transactions.-require-1-of-2-conditions---address-|-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list token holder. Require 1 of 2 conditions - address | hassh

> Code samples

```shell
# You can also use wget
curl -X GET /api/token-holders

```

```javascript
const fetch = require('node-fetch');

fetch('/api/token-holders',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/token-holders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/token-holders',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/token-holders', params={

)

print r.json()

```

`GET /api/token-holders`

<h3 id="get-list-token-holder.-require-1-of-2-conditions---address-|-hassh-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|false|token address|
|hash|path|string|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-token-holder.-require-1-of-2-conditions---address-|-hassh-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-blocks">Blocks</h1>

Blocks API

## Get list blocks

> Code samples

```shell
# You can also use wget
curl -X GET /api/blocks

```

```javascript
const fetch = require('node-fetch');

fetch('/api/blocks',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/blocks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/blocks',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/blocks', params={

)

print r.json()

```

`GET /api/blocks`

<h3 id="get-list-blocks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-blocks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get block detail

> Code samples

```shell
# You can also use wget
curl -X GET /api/blocks/{hash}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/blocks/{hash}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/blocks/{hash}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/blocks/{hash}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/blocks/{hash}', params={

)

print r.json()

```

`GET /api/blocks/{hash}`

<h3 id="get-block-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|block number or block hash|

<h3 id="get-block-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list signers of a block

> Code samples

```shell
# You can also use wget
curl -X GET /api/blocks/signers/{blockNumber}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/blocks/signers/{blockNumber}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/blocks/signers/{blockNumber}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/blocks/signers/{blockNumber}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/blocks/signers/{blockNumber}', params={

)

print r.json()

```

`GET /api/blocks/signers/{blockNumber}`

<h3 id="get-list-signers-of-a-block-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blockNumber|path|number|true|account address|

<h3 id="get-list-signers-of-a-block-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-transactions">Transactions</h1>

Transactions API

## Get list blocks. Params limit & page & ((address & tx_account) | block | type)

> Code samples

```shell
# You can also use wget
curl -X GET /api/txs

```

```javascript
const fetch = require('node-fetch');

fetch('/api/txs',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/txs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/txs',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/txs', params={

)

print r.json()

```

`GET /api/txs`

<h3 id="get-list-blocks.-params-limit-&-page-&-((address-&-tx_account)-|-block-|-type)-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|
|address|query|string|false|list tx of address, group with tx_account|
|tx_account|query|string|false|in|out, default = all, group with address|
|block|query|number|false|list tx of a block|
|type|query|string|false|signTxs|otherTxs|pending|all|

<h3 id="get-list-blocks.-params-limit-&-page-&-((address-&-tx_account)-|-block-|-type)-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get transaction detail

> Code samples

```shell
# You can also use wget
curl -X GET /api/txs/{hash}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/txs/{hash}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/txs/{hash}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/txs/{hash}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/txs/{hash}', params={

)

print r.json()

```

`GET /api/txs/{hash}`

<h3 id="get-transaction-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|transaction hash|

<h3 id="get-transaction-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-tokens">Tokens</h1>

Tokens API

## Get token detail

> Code samples

```shell
# You can also use wget
curl -X GET /api/tokens/{hash}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/tokens/{hash}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/tokens/{hash}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/tokens/{hash}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/tokens/{hash}', params={

)

print r.json()

```

`GET /api/tokens/{hash}`

<h3 id="get-token-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|token address|

<h3 id="get-token-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-token">Token</h1>

## Get list tokens

> Code samples

```shell
# You can also use wget
curl -X GET /api/tokens

```

```javascript
const fetch = require('node-fetch');

fetch('/api/tokens',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/tokens", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/tokens',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/tokens', params={

)

print r.json()

```

`GET /api/tokens`

<h3 id="get-list-tokens-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-rewards">Rewards</h1>

## Get list rewards of a voter

> Code samples

```shell
# You can also use wget
curl -X GET /api/rewards/{voter}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/rewards/{voter}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/rewards/{voter}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/rewards/{voter}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/rewards/{voter}', params={

)

print r.json()

```

`GET /api/rewards/{voter}`

<h3 id="get-list-rewards-of-a-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|number|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-rewards-of-a-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list reward of an epoch

> Code samples

```shell
# You can also use wget
curl -X GET /api/rewards/epoch/{epochNumber}

```

```javascript
const fetch = require('node-fetch');

fetch('/api/rewards/epoch/{epochNumber}',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/rewards/epoch/{epochNumber}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/api/rewards/epoch/{epochNumber}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('/api/rewards/epoch/{epochNumber}', params={

)

print r.json()

```

`GET /api/rewards/epoch/{epochNumber}`

<h3 id="get-list-reward-of-an-epoch-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|epochNumber|path|number|true|epoch number|
|hash|path|string|true|account address|

<h3 id="get-list-reward-of-an-epoch-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>


<h1 id="tomomaster-apis">TomoMaster APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Happy to code TomoMaster APIs

License: <a href="https://github.com/tomochain/tomomaster">Github</a>

Base URL: https://master.tomochain.com

Swagger API Document: [https://master.tomochain.com/api-docs/](https://master.tomochain.com/api-docs/)

<h1 id="tomomaster-apis-config">Config</h1>

Get TomoMaster Application Configuration

## Get TomoMaster Application Configuration

> Code samples

```shell
# You can also use wget
curl -X GET /api/config \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/config',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/config", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/config',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/config', params={

}, headers = headers)

print r.json()

```

`GET /api/config`

> Example responses

> 200 Response

```json
{
  "blockchain": {
    "rpc": "string",
    "ws": "string",
    "epoch": 900,
    "blockTime": 0
  },
  "explorerUrl": "string",
  "GA": "string"
}
```

<h3 id="get-tomomaster-application-configuration-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[config](#schemaconfig)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-candidates">Candidates</h1>

Get Candidates information

## Get candidates information

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates`

<h3 id="get-candidates-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "123",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "91540333800000001000000",
      "createdAt": "2018-10-31T03:42:39.375Z",
      "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
      "status": "RESIGNED",
      "updatedAt": "2019-01-11T09:21:55.028Z",
      "latestSignedBlock": 2917487,
      "capacityNumber": 91540.33380000001,
      "isMasternode": false,
      "isPenalty": false
    }
  ],
  "total": 100,
  "activeCandidates": 10
}
```

<h3 id="get-candidates-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidate](#schemacandidate)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get candidate's information

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates/{candidate} \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates/{candidate}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates/{candidate}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates/{candidate}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates/{candidate}', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates/{candidate}`

<h3 id="get-candidate's-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
{
  "_id": "123",
  "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "91540333800000001000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
  "status": "RESIGNED",
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "latestSignedBlock": "2917487",
  "capacityNumber": 91540.33380000001,
  "isMasternode": false,
  "isPenalty": false
}
```

<h3 id="get-candidate's-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateDetail](#schemacandidatedetail)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get voters who voted for the candidate

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates/{candidate}/voters \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates/{candidate}/voters',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates/{candidate}/voters", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates/{candidate}/voters',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates/{candidate}/voters', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates/{candidate}/voters`

<h3 id="get-voters-who-voted-for-the-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5bd924a9aa41b819395d9207",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "voter": "0xf2cce442c7ab5baf194838081b5f9396330ecfb8",
      "__v": 0,
      "capacity": "105000000000000000000",
      "createdAt": "2018-10-31T03:42:33.922Z",
      "updatedAt": "2019-01-05T02:11:31.489Z",
      "capacityNumber": 105
    }
  ],
  "total": 100
}
```

<h3 id="get-voters-who-voted-for-the-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateVoter](#schemacandidatevoter)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Masternode checking

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates/{candidate}/isMasternode \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates/{candidate}/isMasternode',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates/{candidate}/isMasternode", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates/{candidate}/isMasternode',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates/{candidate}/isMasternode', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates/{candidate}/isMasternode`

<h3 id="masternode-checking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
"1"
```

<h3 id="masternode-checking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[isMasternode](#schemaismasternode)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Candidate checking

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates/{candidate}/isCandidate \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates/{candidate}/isCandidate',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates/{candidate}/isCandidate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates/{candidate}/isCandidate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates/{candidate}/isCandidate', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates/{candidate}/isCandidate`

<h3 id="candidate-checking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
"1"
```

<h3 id="candidate-checking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[isCandidate](#schemaiscandidate)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get reward of candidate

> Code samples

```shell
# You can also use wget
curl -X GET /api/candidates/{candidate}/{owner}/getRewards \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/candidates/{candidate}/{owner}/getRewards',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/candidates/{candidate}/{owner}/getRewards", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/candidates/{candidate}/{owner}/getRewards',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/candidates/{candidate}/{owner}/getRewards', params={

}, headers = headers)

print r.json()

```

`GET /api/candidates/{candidate}/{owner}/getRewards`

<h3 id="get-reward-of-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|owner|path|string|true|owner's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be9216",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "Voter",
      "lockBalance": "1000",
      "reward": "8.03540381764608993247",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.435Z",
      "updatedAt": "2018-12-18T23:36:31.435Z"
    }
  ],
  "total": 100
}
```

<h3 id="get-reward-of-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateRewards](#schemacandidaterewards)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-voters">Voters</h1>

Get Voter information

## Get voted candidates

> Code samples

```shell
# You can also use wget
curl -X GET /api/voters/{voter}/candidates \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/voters/{voter}/candidates',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/voters/{voter}/candidates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/voters/{voter}/candidates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/voters/{voter}/candidates', params={

}, headers = headers)

print r.json()

```

`GET /api/voters/{voter}/candidates`

<h3 id="get-voted-candidates-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|voter's address|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000000000000000000",
      "capacityNumber": 10,
      "candidateName": "Earth"
    }
  ],
  "total": 100
}
```

<h3 id="get-voted-candidates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[voterCandidates](#schemavotercandidates)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get reward of voter

> Code samples

```shell
# You can also use wget
curl -X GET /api/voters/{voter}/rewards \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/voters/{voter}/rewards',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/voters/{voter}/rewards", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/voters/{voter}/rewards',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/voters/{voter}/rewards', params={

}, headers = headers)

print r.json()

```

`GET /api/voters/{voter}/rewards`

<h3 id="get-reward-of-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|candidate's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be922a",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "MasterNode",
      "lockBalance": "1000",
      "reward": "25.97042513863216266174",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.580Z",
      "updatedAt": "2018-12-18T23:36:31.580Z",
      "candidateName": "0x11621900588eca4410c00097a9f59237f34064cd"
    }
  ],
  "total": 100
}
```

<h3 id="get-reward-of-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[voterRewards](#schemavoterrewards)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-transaction">Transaction</h1>

Get transactions of candidate and voter

## Get transactions of a candidate

> Code samples

```shell
# You can also use wget
curl -X GET /api/transactions/candidate/{candidate} \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/transactions/candidate/{candidate}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/transactions/candidate/{candidate}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/transactions/candidate/{candidate}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/transactions/candidate/{candidate}', params={

}, headers = headers)

print r.json()

```

`GET /api/transactions/candidate/{candidate}`

<h3 id="get-transactions-of-a-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c247c545e769d2f2c10ab38",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0x0f96e419c89dcf1397a6206959334a4485c5a158a0320cb8a8e98db3b7888141",
      "event": "Vote",
      "voter": "0xe91dc9746eed1b5971aabd6e1681da1a4d06be8d",
      "owner": "",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "capacity": "11000000000000000000",
      "blockNumber": 2897395,
      "createdAt": "2018-12-27T07:16:36.000Z",
      "__v": 0
    }
  ],
  "total": 100
}
```

<h3 id="get-transactions-of-a-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[txCandidate](#schematxcandidate)|

<aside class="success">
This operation does not require authentication
</aside>

## Get transactions of a voter

> Code samples

```shell
# You can also use wget
curl -X GET /api/transactions/voter/{voter} \
  -H 'Accept: application/json'

```

```javascript
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/api/transactions/voter/{voter}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/transactions/voter/{voter}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/api/transactions/voter/{voter}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/transactions/voter/{voter}', params={

}, headers = headers)

print r.json()

```

`GET /api/transactions/voter/{voter}`

<h3 id="get-transactions-of-a-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|voter's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c24a189ff305840a2498bf0",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0xf8f2d402c6b1cb5f891b687d69ddcd920e58d9e9fe002857cac0e7ce47998884",
      "event": "Unvote",
      "voter": "0x487d62d33467c4842c5e54eb370837e4e88bba0f",
      "owner": "",
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000999000000000000000",
      "blockNumber": 763397,
      "createdAt": "2018-12-27T09:55:21.000Z",
      "__v": 0
    }
  ],
  "total": 100
}
```

<h3 id="get-transactions-of-a-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[txVoter](#schematxvoter)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSconfig">config</h2>

<a id="schemaconfig"></a>

```json
{
  "blockchain": {
    "rpc": "string",
    "ws": "string",
    "epoch": 900,
    "blockTime": 0
  },
  "explorerUrl": "string",
  "GA": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|blockchain|object|false|none|Tomochain's configurations|
|» rpc|string|false|none|rpc|
|» ws|string|false|none|websocket|
|» epoch|number|false|none|Number of blocks for 1 epoch|
|» blockTime|number|false|none|Block time|
|explorerUrl|string|false|none|Tomoscan's API|
|GA|string|false|none|Google Analytic code|

<h2 id="tocScandidate">candidate</h2>

<a id="schemacandidate"></a>

```json
{
  "items": [
    {
      "_id": "123",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "91540333800000001000000",
      "createdAt": "2018-10-31T03:42:39.375Z",
      "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
      "status": "RESIGNED",
      "updatedAt": "2019-01-11T09:21:55.028Z",
      "latestSignedBlock": 2917487,
      "capacityNumber": 91540.33380000001,
      "isMasternode": false,
      "isPenalty": false
    }
  ],
  "total": 100,
  "activeCandidates": 10
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of candidate|
|activeCandidates|number|false|none|Number of active candidate|

<h2 id="tocScandidatedetail">candidateDetail</h2>

<a id="schemacandidatedetail"></a>

```json
{
  "_id": "123",
  "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "91540333800000001000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
  "status": "RESIGNED",
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "latestSignedBlock": "2917487",
  "capacityNumber": 91540.33380000001,
  "isMasternode": false,
  "isPenalty": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|false|none|id|
|candidate|string|false|none|candidate's address|
|smartContractAddress|string|false|none|smart contract's address|
|__v|number|false|none|__v|
|capacity|string|false|none|capacity in wei|
|createdAt|string|false|none|creation date of candidate|
|owner|string|false|none|owner's address|
|status|string|false|none|candidate's status|
|updatedAt|string|false|none|update time|
|latestSignedBlock|string|false|none|latest signed block|
|capacityNumber|number|false|none|capacity number|
|isMasternode|boolean|false|none|is masternode|
|isPenalty|boolean|false|none|is penalty|

<h2 id="tocScandidaterewards">candidateRewards</h2>

<a id="schemacandidaterewards"></a>

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be9216",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "Voter",
      "lockBalance": "1000",
      "reward": "8.03540381764608993247",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.435Z",
      "updatedAt": "2018-12-18T23:36:31.435Z"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Number of candidate|

<h2 id="tocScandidatevoter">candidateVoter</h2>

<a id="schemacandidatevoter"></a>

```json
{
  "items": [
    {
      "_id": "5bd924a9aa41b819395d9207",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "voter": "0xf2cce442c7ab5baf194838081b5f9396330ecfb8",
      "__v": 0,
      "capacity": "105000000000000000000",
      "createdAt": "2018-10-31T03:42:33.922Z",
      "updatedAt": "2019-01-05T02:11:31.489Z",
      "capacityNumber": 105
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of voters|

<h2 id="tocSvotercandidates">voterCandidates</h2>

<a id="schemavotercandidates"></a>

```json
{
  "items": [
    {
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000000000000000000",
      "capacityNumber": 10,
      "candidateName": "Earth"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of rewards|

<h2 id="tocSvoterrewards">voterRewards</h2>

<a id="schemavoterrewards"></a>

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be922a",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "MasterNode",
      "lockBalance": "1000",
      "reward": "25.97042513863216266174",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.580Z",
      "updatedAt": "2018-12-18T23:36:31.580Z",
      "candidateName": "0x11621900588eca4410c00097a9f59237f34064cd"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Voter's reward array|
|total|number|false|none|Number of candidate|

<h2 id="tocSismasternode">isMasternode</h2>

<a id="schemaismasternode"></a>

```json
"1"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|0|

<h2 id="tocSiscandidate">isCandidate</h2>

<a id="schemaiscandidate"></a>

```json
"1"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|0|

<h2 id="tocStxcandidate">txCandidate</h2>

<a id="schematxcandidate"></a>

```json
{
  "items": [
    {
      "_id": "5c247c545e769d2f2c10ab38",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0x0f96e419c89dcf1397a6206959334a4485c5a158a0320cb8a8e98db3b7888141",
      "event": "Vote",
      "voter": "0xe91dc9746eed1b5971aabd6e1681da1a4d06be8d",
      "owner": "",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "capacity": "11000000000000000000",
      "blockNumber": 2897395,
      "createdAt": "2018-12-27T07:16:36.000Z",
      "__v": 0
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's transactions array|
|total|number|false|none|Number of candidate|

<h2 id="tocStxvoter">txVoter</h2>

<a id="schematxvoter"></a>

```json
{
  "items": [
    {
      "_id": "5c24a189ff305840a2498bf0",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0xf8f2d402c6b1cb5f891b687d69ddcd920e58d9e9fe002857cac0e7ce47998884",
      "event": "Unvote",
      "voter": "0x487d62d33467c4842c5e54eb370837e4e88bba0f",
      "owner": "",
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000999000000000000000",
      "blockNumber": 763397,
      "createdAt": "2018-12-27T09:55:21.000Z",
      "__v": 0
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's transactions array|
|total|number|false|none|Number of candidate|

