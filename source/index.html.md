---
title: OTRIS API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<h1 id="otris-api">OTRIS API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

description TODO

Base URLs:

* <a href="https://https://otrl.test.co.uk">https://https://otrl.test.co.uk</a>

<h1 id="otris-api-jp">Journey Planner (jp)</h1>

## Get Journey Plans

> Code samples

```shell
# You can also use wget
curl -X POST https://https://otrl.test.co.uk/jp/journey-plan \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Brand-Id: ontrackretail'

```

```http
POST https://https://otrl.test.co.uk/jp/journey-plan HTTP/1.1
Host: https://otrl.test.co.uk
Content-Type: application/json
Accept: application/json
X-Brand-Id: ontrackretail

```

```javascript
const inputBody = '{
  "origin": "1512",
  "destination": "5268",
  "outward": {
    "rangeStart": "2020-02-14T10:09:00",
    "rangeEnd": "2020-02-14T13:09:00",
    "arriveDepart": "Depart"
  },
  "return": null,
  "openReturn": false,
  "adults": 1,
  "children": 0,
  "disableGroupSavings": true,
  "numJourneys": 1,
  "railcards": [
    "NEW"
  ],
  "preferences": {
    "via": "5148",
    "avoid": null
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-Brand-Id':'ontrackretail'

};

fetch('https://https://otrl.test.co.uk/jp/journey-plan',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'X-Brand-Id' => 'ontrackretail'
}

result = RestClient.post 'https://https://otrl.test.co.uk/jp/journey-plan',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-Brand-Id': 'ontrackretail'
}

r = requests.post('https://https://otrl.test.co.uk/jp/journey-plan', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'X-Brand-Id' => 'ontrackretail',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://https://otrl.test.co.uk/jp/journey-plan', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://https://otrl.test.co.uk/jp/journey-plan");
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
        "X-Brand-Id": []string{"ontrackretail"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://https://otrl.test.co.uk/jp/journey-plan", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /jp/journey-plan`

Returns valid journeys and fares

> Body parameter

```json
{
  "origin": "1512",
  "destination": "5268",
  "outward": {
    "rangeStart": "2020-02-14T10:09:00",
    "rangeEnd": "2020-02-14T13:09:00",
    "arriveDepart": "Depart"
  },
  "return": null,
  "openReturn": false,
  "adults": 1,
  "children": 0,
  "disableGroupSavings": true,
  "numJourneys": 1,
  "railcards": [
    "NEW"
  ],
  "preferences": {
    "via": "5148",
    "avoid": null
  }
}
```

<h3 id="get-journey-plans-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-Brand-Id|header|string|true|none|
|body|body|[JourenyPlanRequest](#schemajourenyplanrequest)|true|none|

> Example responses

> OK

```json
{
  "result": {
    "outward": [
      {
        "journey": "/jp/journeys/200214%7C1013%7C200214%7C1237%7CTRIP%7CBDM%7CSTP%7C200214%7C1013%7C200214%7C1051%7CEM3205%7CEM%7CTRANSFER%7CSTP%7CVIC%7C41%7CUnderground%7CTRIP%7CVIC%7CBTN%7C200214%7C1144%7C200214%7C1237%7CGX0233%7CGX",
        "fares": {
          "singles": [
            "/jp/fares/0410%3A5268%3AFDS%3A00000%3A%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A7320%2C1%2C0%2C000%2C%2C%2C%7CIKED1sCzXsWGXoHqFwc5Uh74zbI%3D",
            "/jp/fares/0410%3A5268%3ASDS%3A00000%3A%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A3015%2C1%2C0%2C048%2CNEW%2C%2C1555%7CckY9Aex6UijdnD2eVm%2Fn1ucWSxY%3D",
            "/jp/fares/0410%3A5268%3ACDS%3A00000%3AC4%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A2560%2C1%2C0%2C048%2CNEW%2C%2C1320%7CsuQtn2ivqby7Ubrs%2Fp16OtFBLhA%3D"
          ],
          "returns": [],
          "cheapest": {
            "outwardSingle": "/jp/fares/0410%3A5268%3ACDS%3A00000%3AC4%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A2560%2C1%2C0%2C048%2CNEW%2C%2C1320%7CsuQtn2ivqby7Ubrs%2Fp16OtFBLhA%3D",
            "inboundSingle": null,
            "return": null,
            "totalPrice": 2560
          }
        }
      }
    ],
    "return": [],
    "useServiceProvider": false
  },
  "links": null
}
```

```json
{
  "result": {
    "outward": [
      {
        "journey": "/jp/journeys/200214%7C1013%7C200214%7C1237%7CTRIP%7CBDM%7CSTP%7C200214%7C1013%7C200214%7C1051%7CEM3205%7CEM%7CTRANSFER%7CSTP%7CVIC%7C41%7CUnderground%7CTRIP%7CVIC%7CBTN%7C200214%7C1144%7C200214%7C1237%7CGX0233%7CGX",
        "fares": {
          "singles": [
            "/jp/fares/0410%3A5268%3AFDS%3A00000%3A%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A7320%2C1%2C0%2C000%2C%2C%2C%7CIKED1sCzXsWGXoHqFwc5Uh74zbI%3D",
            "/jp/fares/0410%3A5268%3ASDS%3A00000%3A%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A3015%2C1%2C0%2C048%2CNEW%2C%2C1555%7CckY9Aex6UijdnD2eVm%2Fn1ucWSxY%3D",
            "/jp/fares/0410%3A5268%3ACDS%3A00000%3AC4%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A2560%2C1%2C0%2C048%2CNEW%2C%2C1320%7CsuQtn2ivqby7Ubrs%2Fp16OtFBLhA%3D"
          ],
          "returns": [
            "/jp/fares/0410%3A5268%3ASVR%3A00000%3A4J%3A1%3A20200214%3A20200214%3A0001%3A20200214%3A20200313%3A0100%3A%3A%3A%3A%3A2990%2C1%2C0%2C048%2CNEW%2C%2C1540%7CBDXHPPSyVSkT5cD%2FhwTmwZjTIaY%3D"
          ],
          "cheapest": {
            "return": "/jp/fares/0410%3A5268%3ASVR%3A00000%3A4J%3A1%3A20200214%3A20200214%3A0001%3A20200214%3A20200313%3A0100%3A%3A%3A%3A%3A2990%2C1%2C0%2C048%2CNEW%2C%2C1540%7CBDXHPPSyVSkT5cD%2FhwTmwZjTIaY%3D",
            "totalPrice": 2990
          }
        }
      }
    ],
    "return": [
      {
        "journey": "/jp/journeys/200215%7C1018%7C200215%7C1244%7CTRIP%7CBTN%7CVIC%7C200215%7C1018%7C200215%7C1113%7CGX0297%7CGX%7CTRANSFER%7CVIC%7CSTP%7C41%7CUnderground%7CTRIP%7CSTP%7CBDM%7C200215%7C1202%7C200215%7C1244%7CEM7112%7CEM",
        "fares": {
          "singles": [
            "/jp/fares/5268%3A0410%3ACBB%3A00000%3AFB%3A1%3A20200215%3A20200215%3A0001%3A%3A%3A%3A%3A%3A%3A%3A1505%2C1%2C0%2C048%2CNEW%2C%2C775%7Cq1fbjIV1g0fPGUH1BHTFcUNwsCo%3D",
            "/jp/fares/5268%3A0410%3AFDS%3A00000%3A%3A1%3A20200215%3A20200215%3A0001%3A%3A%3A%3A%3A%3A%3A%3A7320%2C1%2C0%2C000%2C%2C%2C%7CuTLUGI8pqHc4KXiOgrmpVKOLgns%3D",
            "/jp/fares/5268%3A0410%3ASDS%3A00000%3A%3A1%3A20200215%3A20200215%3A0001%3A%3A%3A%3A%3A%3A%3A%3A3015%2C1%2C0%2C048%2CNEW%2C%2C1555%7Coa%2BSmkHriCa28AQDPajj%2BGj32cg%3D",
            "/jp/fares/5268%3A0410%3ACDS%3A00000%3AB3%3A1%3A20200215%3A20200215%3A0001%3A%3A%3A%3A%3A%3A%3A%3A2560%2C1%2C0%2C048%2CNEW%2C%2C1320%7Czjbn7vcfVho9nhCOlvhXb1gcI%2FQ%3D"
          ],
          "returns": [
            "/jp/fares/0410%3A5268%3ASVR%3A00000%3A4J%3A1%3A20200214%3A20200214%3A0001%3A20200214%3A20200313%3A0100%3A%3A%3A%3A%3A2990%2C1%2C0%2C048%2CNEW%2C%2C1540%7CBDXHPPSyVSkT5cD%2FhwTmwZjTIaY%3D"
          ],
          "cheapest": {
            "outwardSingle": "/jp/fares/0410%3A5268%3ACDS%3A00000%3AC4%3A1%3A20200214%3A20200214%3A0001%3A%3A%3A%3A%3A%3A%3A%3A2560%2C1%2C0%2C048%2CNEW%2C%2C1320%7CsuQtn2ivqby7Ubrs%2Fp16OtFBLhA%3D",
            "inboundSingle": "/jp/fares/5268%3A0410%3ACBB%3A00000%3AFB%3A1%3A20200215%3A20200215%3A0001%3A%3A%3A%3A%3A%3A%3A%3A1505%2C1%2C0%2C048%2CNEW%2C%2C775%7Cq1fbjIV1g0fPGUH1BHTFcUNwsCo%3D",
            "totalPrice": 4065
          }
        }
      }
    ],
    "useServiceProvider": false
  }
}
```

<h3 id="get-journey-plans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[JourenyPlanResponse](#schemajourenyplanresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## Get Journey By Id

> Code samples

```shell
# You can also use wget
curl -X GET https://https://otrl.test.co.uk/jp/journeys/{id} \
  -H 'Accept: application/json' \
  -H 'X-Brand-Id: ontrackretail'

```

```http
GET https://https://otrl.test.co.uk/jp/journeys/{id} HTTP/1.1
Host: https://otrl.test.co.uk
Accept: application/json
X-Brand-Id: ontrackretail

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-Brand-Id':'ontrackretail'

};

fetch('https://https://otrl.test.co.uk/jp/journeys/{id}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Brand-Id' => 'ontrackretail'
}

result = RestClient.get 'https://https://otrl.test.co.uk/jp/journeys/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Brand-Id': 'ontrackretail'
}

r = requests.get('https://https://otrl.test.co.uk/jp/journeys/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-Brand-Id' => 'ontrackretail',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://https://otrl.test.co.uk/jp/journeys/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://https://otrl.test.co.uk/jp/journeys/{id}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Brand-Id": []string{"ontrackretail"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://https://otrl.test.co.uk/jp/journeys/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /jp/journeys/{id}`

Returns a journey based on a single ID

<h3 id="get-journey-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-Brand-Id|header|string|true|none|
|id|path|string|true|ID of pet to fetch|

> Example responses

> OK

```json
{
  "result": {
    "origin": {
      "station": "/data/stations/1512",
      "time": {
        "scheduledTime": "2020-02-14T10:19:00",
        "adjustedTime": "2020-02-14T10:19:00",
        "confidence": "Estimate",
        "delayed": false
      }
    },
    "destination": {
      "station": "/data/stations/5268",
      "time": {
        "scheduledTime": "2020-02-14T12:42:00",
        "adjustedTime": "2020-02-14T12:42:00",
        "confidence": "Estimate",
        "delayed": false
      }
    },
    "changes": 1,
    "legs": [
      {
        "origin": [
          {
            "station": "/data/stations/1512",
            "time": {
              "scheduledTime": "2020-02-14T10:19:00",
              "adjustedTime": "2020-02-14T10:19:00",
              "confidence": "Estimate",
              "delayed": false
            }
          }
        ],
        "destination": [
          {
            "station": "/data/stations/5268",
            "time": {
              "scheduledTime": "2020-02-14T12:42:00",
              "adjustedTime": "2020-02-14T12:42:00",
              "confidence": "Estimate",
              "delayed": false
            }
          }
        ],
        "serviceDetails": {
          "mode": "Train",
          "retailServiceId": "TL370900",
          "trainUid": "W40845",
          "toc": "/data/tocs/TL",
          "reservable": "No",
          "isTemporaryTrain": false,
          "isCountedPlace": false
        },
        "fixed": false,
        "id": "1512;5268;2020-02-14;"
      }
    ],
    "callingPoints": "/jp/journeys/45%3ABDM_BTN_W40845/calling-points",
    "isOvertaken": false,
    "bulletins": [
      {
        "id": "3CC58359676B4C23BB8D2CE2342F3390",
        "title": "\"Disruption between London St Pancras International and Bedford expected\nuntil the end of the day\"\n",
        "description": "NRE Incidents",
        "url": "https://www.nationalrail.co.uk/service_disruptions/241980.aspx",
        "category": "Disruption"
      }
    ],
    "status": "successful",
    "isCancelled": false
  },
  "links": null
}
```

<h3 id="get-journey-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Journey](#schemajourney)|

<aside class="success">
This operation does not require authentication
</aside>

## Get Fare By Id

> Code samples

```shell
# You can also use wget
curl -X GET https://https://otrl.test.co.uk/jp/fares/{id} \
  -H 'Accept: application/json' \
  -H 'X-Brand-Id: ontrackretail'

```

```http
GET https://https://otrl.test.co.uk/jp/fares/{id} HTTP/1.1
Host: https://otrl.test.co.uk
Accept: application/json
X-Brand-Id: ontrackretail

```

```javascript

const headers = {
  'Accept':'application/json',
  'X-Brand-Id':'ontrackretail'

};

fetch('https://https://otrl.test.co.uk/jp/fares/{id}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'X-Brand-Id' => 'ontrackretail'
}

result = RestClient.get 'https://https://otrl.test.co.uk/jp/fares/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'X-Brand-Id': 'ontrackretail'
}

r = requests.get('https://https://otrl.test.co.uk/jp/fares/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'X-Brand-Id' => 'ontrackretail',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://https://otrl.test.co.uk/jp/fares/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://https://otrl.test.co.uk/jp/fares/{id}");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "X-Brand-Id": []string{"ontrackretail"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://https://otrl.test.co.uk/jp/fares/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /jp/fares/{id}`

Returns a fare based on a single ID

<h3 id="get-fare-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|X-Brand-Id|header|string|true|none|
|id|path|string|true|ID of pet to fetch|

> Example responses

> OK

```json
{
  "result": {
    "origin": "/data/stations/0410",
    "alternateOrigins": [
      "/data/stations/1510",
      "/data/stations/1512"
    ],
    "destination": "/data/stations/5268",
    "alternateDestination": null,
    "ticketType": "/data/ticket-types/SVR",
    "route": "/data/routes/00000",
    "restriction": null,
    "crossLondon": true,
    "outwardValidity": {
      "from": "2020-02-14",
      "until": "2020-02-14",
      "period": {
        "days": 1
      },
      "break": true
    },
    "returnValidity": {
      "from": "2020-02-14",
      "until": "2020-03-13",
      "period": {
        "months": 1
      },
      "break": true
    },
    "tickets": [
      {
        "price": 2990,
        "adults": 1,
        "children": 0,
        "statusCode": 48,
        "isFirstClass": false,
        "railcard": "/data/railcards/NEW",
        "railcardDiscount": 1540
      }
    ],
    "totalPrice": 2990,
    "originalTotalPrice": 2990,
    "category": "OffPeak",
    "seatAvailability": null
  },
  "links": null
}
```

<h3 id="get-fare-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Fare](#schemafare)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_JourenyPlanRequest">JourenyPlanRequest</h2>
<!-- backwards compatibility -->
<a id="schemajourenyplanrequest"></a>
<a id="schema_JourenyPlanRequest"></a>
<a id="tocSjourenyplanrequest"></a>
<a id="tocsjourenyplanrequest"></a>

```json
{
  "origin": "string",
  "destination": "string",
  "outward": {
    "rangeStart": "string",
    "rangeEnd": "string",
    "arriveDepart": "Arrive"
  },
  "return": {
    "rangeStart": "string",
    "rangeEnd": "string",
    "arriveDepart": "Arrive"
  },
  "openReturn": true,
  "adults": 0,
  "children": 0,
  "disableGroupSavings": true,
  "numJourneys": 0,
  "railcards": [
    "string"
  ],
  "preferences": {
    "via": "string",
    "avoid": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|origin|string|true|none|none|
|destination|string|true|none|none|
|outward|[Timeband](#schematimeband)|true|none|none|
|return|[Timeband](#schematimeband)|false|none|none|
|openReturn|boolean|false|none|none|
|adults|integer(int64)|true|none|none|
|children|integer(int64)|true|none|none|
|disableGroupSavings|boolean|false|none|none|
|numJourneys|integer(int64)|true|none|none|
|railcards|[string]|false|none|none|
|preferences|[JourneyPlanPreferences](#schemajourneyplanpreferences)|false|none|none|

<h2 id="tocS_Timeband">Timeband</h2>
<!-- backwards compatibility -->
<a id="schematimeband"></a>
<a id="schema_Timeband"></a>
<a id="tocStimeband"></a>
<a id="tocstimeband"></a>

```json
{
  "rangeStart": "string",
  "rangeEnd": "string",
  "arriveDepart": "Arrive"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|rangeStart|string|false|none|none|
|rangeEnd|string|false|none|none|
|arriveDepart|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|arriveDepart|Arrive|
|arriveDepart|Depart|

<h2 id="tocS_JourneyPlanPreferences">JourneyPlanPreferences</h2>
<!-- backwards compatibility -->
<a id="schemajourneyplanpreferences"></a>
<a id="schema_JourneyPlanPreferences"></a>
<a id="tocSjourneyplanpreferences"></a>
<a id="tocsjourneyplanpreferences"></a>

```json
{
  "via": "string",
  "avoid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|via|string|false|none|none|
|avoid|string|false|none|none|

<h2 id="tocS_JourenyPlanResponse">JourenyPlanResponse</h2>
<!-- backwards compatibility -->
<a id="schemajourenyplanresponse"></a>
<a id="schema_JourenyPlanResponse"></a>
<a id="tocSjourenyplanresponse"></a>
<a id="tocsjourenyplanresponse"></a>

```json
{
  "result": {
    "outward": [
      {
        "journey": "string",
        "fares": {
          "singles": [
            "string"
          ],
          "returns": [
            "string"
          ],
          "cheapest": {
            "outwardSingle": "string",
            "inboundSingle": "string",
            "return": "string",
            "totalPrice": 0
          }
        },
        "oysterPrice": 0
      }
    ],
    "return": [
      {
        "journey": "string",
        "fares": {
          "singles": [
            "string"
          ],
          "returns": [
            "string"
          ],
          "cheapest": {
            "outwardSingle": "string",
            "inboundSingle": "string",
            "return": "string",
            "totalPrice": 0
          }
        },
        "oysterPrice": 0
      }
    ],
    "useServiceProvider": true
  },
  "links": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|result|object|false|none|none|
|» outward|[[JourneyPlan](#schemajourneyplan)]|false|none|none|
|» return|[[JourneyPlan](#schemajourneyplan)]|false|none|none|
|» useServiceProvider|boolean|false|none|none|
|links|object|false|none|none|

<h2 id="tocS_JourneyPlan">JourneyPlan</h2>
<!-- backwards compatibility -->
<a id="schemajourneyplan"></a>
<a id="schema_JourneyPlan"></a>
<a id="tocSjourneyplan"></a>
<a id="tocsjourneyplan"></a>

```json
{
  "journey": "string",
  "fares": {
    "singles": [
      "string"
    ],
    "returns": [
      "string"
    ],
    "cheapest": {
      "outwardSingle": "string",
      "inboundSingle": "string",
      "return": "string",
      "totalPrice": 0
    }
  },
  "oysterPrice": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|journey|string|false|none|none|
|fares|object|false|none|none|
|» singles|[string]|false|none|none|
|» returns|[string]|false|none|none|
|» cheapest|object|false|none|none|
|»» outwardSingle|string|false|none|none|
|»» inboundSingle|string|false|none|none|
|»» return|string|false|none|none|
|»» totalPrice|integer(int64)|false|none|none|
|oysterPrice|integer(int64)|false|none|none|

<h2 id="tocS_AdjustedTime">AdjustedTime</h2>
<!-- backwards compatibility -->
<a id="schemaadjustedtime"></a>
<a id="schema_AdjustedTime"></a>
<a id="tocSadjustedtime"></a>
<a id="tocsadjustedtime"></a>

```json
{
  "scheduledTime": "string",
  "adjustedTime": "string",
  "confidence": "Actual",
  "delayed": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|scheduledTime|string|true|none|none|
|adjustedTime|string|true|none|none|
|confidence|string|true|none|none|
|delayed|boolean|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|confidence|Actual|
|confidence|Estimate|
|confidence|Uncertain|

<h2 id="tocS_Stop">Stop</h2>
<!-- backwards compatibility -->
<a id="schemastop"></a>
<a id="schema_Stop"></a>
<a id="tocSstop"></a>
<a id="tocsstop"></a>

```json
{
  "station": "string",
  "time": {
    "scheduledTime": "string",
    "adjustedTime": "string",
    "confidence": "Actual",
    "delayed": true
  },
  "pattern": "Passing",
  "boardAlight": "Board",
  "platform": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|station|string|true|none|none|
|time|[AdjustedTime](#schemaadjustedtime)|false|none|none|
|pattern|string|false|none|none|
|boardAlight|string|false|none|none|
|platform|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|pattern|Passing|
|pattern|PickUpOnly|
|pattern|SetDownOnly|
|pattern|Normal|
|pattern|RequestStop|
|boardAlight|Board|
|boardAlight|Alight|

<h2 id="tocS_Leg">Leg</h2>
<!-- backwards compatibility -->
<a id="schemaleg"></a>
<a id="schema_Leg"></a>
<a id="tocSleg"></a>
<a id="tocsleg"></a>

```json
{
  "id": "string",
  "origin": [
    {
      "station": "string",
      "time": {
        "scheduledTime": "string",
        "adjustedTime": "string",
        "confidence": "Actual",
        "delayed": true
      },
      "pattern": "Passing",
      "boardAlight": "Board",
      "platform": "string"
    }
  ],
  "destination": [
    {
      "station": "string",
      "time": {
        "scheduledTime": "string",
        "adjustedTime": "string",
        "confidence": "Actual",
        "delayed": true
      },
      "pattern": "Passing",
      "boardAlight": "Board",
      "platform": "string"
    }
  ],
  "serviceDetails": {
    "mode": "Train",
    "retailServiceId": "string",
    "trainUid": "string",
    "toc": "string",
    "reservable": "Compulsory",
    "isTemporaryTrain": true,
    "isCountedPlace": true
  },
  "fixed": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|origin|[[Stop](#schemastop)]|true|none|none|
|destination|[[Stop](#schemastop)]|true|none|none|
|serviceDetails|object|true|none|none|
|» mode|string|true|none|none|
|» retailServiceId|string|false|none|none|
|» trainUid|string|false|none|none|
|» toc|string|false|none|none|
|» reservable|string|false|none|none|
|» isTemporaryTrain|boolean|false|none|none|
|» isCountedPlace|boolean|false|none|none|
|fixed|boolean|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|mode|Train|
|mode|Metro|
|mode|Bus|
|mode|ReplacementBus|
|mode|Tram|
|mode|Ferry|
|mode|Taxi|
|mode|Walk|
|mode|Other|
|reservable|Compulsory|
|reservable|BicyclesEssential|
|reservable|Recommended|
|reservable|Possible|
|reservable|No|

<h2 id="tocS_Bulletin">Bulletin</h2>
<!-- backwards compatibility -->
<a id="schemabulletin"></a>
<a id="schema_Bulletin"></a>
<a id="tocSbulletin"></a>
<a id="tocsbulletin"></a>

```json
{
  "id": "string",
  "title": "string",
  "description": "string",
  "url": "string",
  "category": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|title|string|true|none|none|
|description|string|false|none|none|
|url|string|true|none|none|
|category|string|false|none|none|

<h2 id="tocS_Journey">Journey</h2>
<!-- backwards compatibility -->
<a id="schemajourney"></a>
<a id="schema_Journey"></a>
<a id="tocSjourney"></a>
<a id="tocsjourney"></a>

```json
{
  "origin": {
    "station": "string",
    "time": {
      "scheduledTime": "string",
      "adjustedTime": "string",
      "confidence": "Actual",
      "delayed": true
    },
    "pattern": "Passing",
    "boardAlight": "Board",
    "platform": "string"
  },
  "destination": {
    "station": "string",
    "time": {
      "scheduledTime": "string",
      "adjustedTime": "string",
      "confidence": "Actual",
      "delayed": true
    },
    "pattern": "Passing",
    "boardAlight": "Board",
    "platform": "string"
  },
  "changes": 0,
  "legs": [
    {
      "id": "string",
      "origin": [
        {
          "station": "string",
          "time": {
            "scheduledTime": "string",
            "adjustedTime": "string",
            "confidence": "Actual",
            "delayed": true
          },
          "pattern": "Passing",
          "boardAlight": "Board",
          "platform": "string"
        }
      ],
      "destination": [
        {
          "station": "string",
          "time": {
            "scheduledTime": "string",
            "adjustedTime": "string",
            "confidence": "Actual",
            "delayed": true
          },
          "pattern": "Passing",
          "boardAlight": "Board",
          "platform": "string"
        }
      ],
      "serviceDetails": {
        "mode": "Train",
        "retailServiceId": "string",
        "trainUid": "string",
        "toc": "string",
        "reservable": "Compulsory",
        "isTemporaryTrain": true,
        "isCountedPlace": true
      },
      "fixed": true
    }
  ],
  "callingPoints": "string",
  "isOvertaken": true,
  "bulletins": [
    {
      "id": "string",
      "title": "string",
      "description": "string",
      "url": "string",
      "category": "string"
    }
  ],
  "status": "string",
  "isCancelled": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|origin|[Stop](#schemastop)|true|none|none|
|destination|[Stop](#schemastop)|true|none|none|
|changes|integer(int64)|true|none|none|
|legs|[[Leg](#schemaleg)]|true|none|none|
|callingPoints|string|true|none|none|
|isOvertaken|boolean|true|none|none|
|bulletins|[[Bulletin](#schemabulletin)]|false|none|none|
|status|string|true|none|none|
|isCancelled|boolean|false|none|none|

<h2 id="tocS_Validity">Validity</h2>
<!-- backwards compatibility -->
<a id="schemavalidity"></a>
<a id="schema_Validity"></a>
<a id="tocSvalidity"></a>
<a id="tocsvalidity"></a>

```json
{
  "from": "string",
  "until": "string",
  "period": {
    "days": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|false|none|none|
|until|string|false|none|none|
|period|object|false|none|none|
|» days|integer(int64)|false|none|none|

<h2 id="tocS_Ticket">Ticket</h2>
<!-- backwards compatibility -->
<a id="schematicket"></a>
<a id="schema_Ticket"></a>
<a id="tocSticket"></a>
<a id="tocsticket"></a>

```json
{
  "price": 0,
  "adults": 0,
  "children": 0,
  "statusCode": "string",
  "isFirstClass": true,
  "railcard": "string",
  "railcardDiscount": 0,
  "totalPrice": 0,
  "originalTotalPrice": 0,
  "category": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|price|integer(int64)|false|none|none|
|adults|integer(int64)|false|none|none|
|children|integer(int64)|false|none|none|
|statusCode|string|false|none|none|
|isFirstClass|boolean|false|none|none|
|railcard|string|false|none|none|
|railcardDiscount|integer(int64)|false|none|none|
|totalPrice|integer(int64)|false|none|none|
|originalTotalPrice|integer(int64)|false|none|none|
|category|string|false|none|none|

<h2 id="tocS_Fare">Fare</h2>
<!-- backwards compatibility -->
<a id="schemafare"></a>
<a id="schema_Fare"></a>
<a id="tocSfare"></a>
<a id="tocsfare"></a>

```json
{
  "origin": "string",
  "alternateOrigins": [
    "string"
  ],
  "destination": "string",
  "alternateDestination": [
    "string"
  ],
  "ticketType": "string",
  "route": "string",
  "restriction": "string",
  "crossLondon": true,
  "outwardValidity": {
    "from": "string",
    "until": "string",
    "period": {
      "days": 0
    }
  },
  "returnValidity": {
    "from": "string",
    "until": "string",
    "period": {
      "days": 0
    }
  },
  "break": true,
  "tickets": [
    {
      "price": 0,
      "adults": 0,
      "children": 0,
      "statusCode": "string",
      "isFirstClass": true,
      "railcard": "string",
      "railcardDiscount": 0,
      "totalPrice": 0,
      "originalTotalPrice": 0,
      "category": "string"
    }
  ],
  "totalPrice": 0,
  "originalTotalPrice": 0,
  "category": "string",
  "seatAvailability": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|origin|string|true|none|none|
|alternateOrigins|[string]|false|none|none|
|destination|string|true|none|none|
|alternateDestination|[string]|false|none|none|
|ticketType|string|true|none|none|
|route|string|true|none|none|
|restriction|string|false|none|none|
|crossLondon|boolean|true|none|none|
|outwardValidity|[Validity](#schemavalidity)|true|none|none|
|returnValidity|[Validity](#schemavalidity)|false|none|none|
|break|boolean|false|none|none|
|tickets|[[Ticket](#schematicket)]|true|none|none|
|totalPrice|integer(int64)|true|none|none|
|originalTotalPrice|integer(int64)|true|none|none|
|category|string|false|none|none|
|seatAvailability|integer(int64)|false|none|none|

