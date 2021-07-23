---
title: Fastcash API v10
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

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="fastcash-api">Fastcash API v10</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Bank Accounts Endpoints

Base URLs:

* <a href="https://dev.meu.cash/apiv10">https://dev.meu.cash/apiv10</a>

Email: <a href="mailto:dev@fastcash.com.br">Support</a> 

# Authentication

* API Key (apikey)
    - Parameter Name: **Authorization**, in: header. APIKey Authentication

<h1 id="fastcash-api-bank-accounts">Bank Accounts</h1>

## ListUsersBankAccounts

<a id="opIdListUsersBankAccounts"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://dev.meu.cash/apiv10/user/listbankaccounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```http
POST https://dev.meu.cash/apiv10/user/listbankaccounts HTTP/1.1
Host: dev.meu.cash
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "Pid": 110,
  "ProdId": 4957,
  "CustomerDocument": null,
  "ExternalCustomerId": null
}
';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'
};

fetch('https://dev.meu.cash/apiv10/user/listbankaccounts',
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
  'Authorization' => 'API_KEY'
}

result = RestClient.post 'https://dev.meu.cash/apiv10/user/listbankaccounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('https://dev.meu.cash/apiv10/user/listbankaccounts', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'Authorization' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://dev.meu.cash/apiv10/user/listbankaccounts', array(
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
URL obj = new URL("https://dev.meu.cash/apiv10/user/listbankaccounts");
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
        "Authorization": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://dev.meu.cash/apiv10/user/listbankaccounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user/listbankaccounts`

> Body parameter

```json
"{\n  \"Pid\": 110,\n  \"ProdId\": 4957,\n  \"CustomerDocument\": null,\n  \"ExternalCustomerId\": null\n}\n"
```

<h3 id="listusersbankaccounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ListUsersBankAccountsRequest](#schemalistusersbankaccountsrequest)|true|none|

> Example responses

> OK

```json
{
  "Errors": null,
  "Result": [
    {
      "BankAccountId": 34,
      "Pid": 110,
      "ProdId": 3509,
      "ExternalCustomerId": "9999",
      "CustomerName": "Johnnie Bayer",
      "CustomerDocument": "157.855.433-03",
      "BankNumber": "341",
      "BankBranchNumber": "3765",
      "BankAccountNumber": "04485-8",
      "BankAccountType": "001",
      "BankAccountHolderName": "Johnnie Bayer",
      "BankAccountHolderDocument": "157.855.433-03",
      "CreatedDate": "2020-08-17T22:43:21.06-03:00",
      "Validated": false,
      "Blacklisted": false,
      "UpdatedDate": null
    }
  ],
  "Success": true,
  "Message": null,
  "StatusCode": 200
}
```

<h3 id="listusersbankaccounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ListUsersBankAccountsReply](#schemalistusersbankaccountsreply)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apikey
</aside>

## GetNearbyBanks

<a id="opIdGetNearbyBanks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://dev.meu.cash/apiv10/nearby/banks?latitude=0&longitude=0 \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```http
GET https://dev.meu.cash/apiv10/nearby/banks?latitude=0&longitude=0 HTTP/1.1
Host: dev.meu.cash
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'
};

fetch('https://dev.meu.cash/apiv10/nearby/banks?latitude=0&longitude=0',
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
  'Authorization' => 'API_KEY'
}

result = RestClient.get 'https://dev.meu.cash/apiv10/nearby/banks',
  params: {
  'latitude' => 'number',
'longitude' => 'number'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('https://dev.meu.cash/apiv10/nearby/banks', params={
  'latitude': '0',  'longitude': '0'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://dev.meu.cash/apiv10/nearby/banks', array(
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
URL obj = new URL("https://dev.meu.cash/apiv10/nearby/banks?latitude=0&longitude=0");
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
        "Authorization": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://dev.meu.cash/apiv10/nearby/banks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /nearby/banks`

<h3 id="getnearbybanks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|latitude|query|number|true|none|
|longitude|query|number|true|none|

> Example responses

> OK

```json
{
  "Result": {
    "Results": [
      {
        "Geometry": {
          "Location": {
            "Lat": -23.5480521,
            "Lng": -46.6592421
          }
        },
        "Name": "Banco Santander - Polo Higienópolis - Agência 2703",
        "OpeningHours": {
          "open_now": false
        },
        "Vicinity": "Avenida Angélica, 1784 - Consolação, São Paulo"
      }
    ],
    "Status": "OK"
  },
  "Success": true,
  "Message": null,
  "StatusCode": 200
}
```

<h3 id="getnearbybanks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GetNearbyBanksReply](#schemagetnearbybanksreply)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apikey
</aside>

# Schemas

<h2 id="tocS_BaseRequest">BaseRequest</h2>
<!-- backwards compatibility -->
<a id="schemabaserequest"></a>
<a id="schema_BaseRequest"></a>
<a id="tocSbaserequest"></a>
<a id="tocsbaserequest"></a>

```json
null

```

### Properties

*None*

<h2 id="tocS_BaseReply">BaseReply</h2>
<!-- backwards compatibility -->
<a id="schemabasereply"></a>
<a id="schema_BaseReply"></a>
<a id="tocSbasereply"></a>
<a id="tocsbasereply"></a>

```json
{
  "Success": true,
  "Message": "string",
  "StatusCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Success|boolean|false|none|none|
|Message|string|false|none|none|
|StatusCode|integer(int32)|false|none|none|

<h2 id="tocS_CompanyConfiguration">CompanyConfiguration</h2>
<!-- backwards compatibility -->
<a id="schemacompanyconfiguration"></a>
<a id="schema_CompanyConfiguration"></a>
<a id="tocScompanyconfiguration"></a>
<a id="tocscompanyconfiguration"></a>

```json
{
  "Pid": 0,
  "ProdId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Pid|integer(int32)|true|none|none|
|ProdId|integer(int32)|true|none|none|

<h2 id="tocS_UserBankAccount">UserBankAccount</h2>
<!-- backwards compatibility -->
<a id="schemauserbankaccount"></a>
<a id="schema_UserBankAccount"></a>
<a id="tocSuserbankaccount"></a>
<a id="tocsuserbankaccount"></a>

```json
{
  "BankAccountId": 0,
  "Pid": 0,
  "ProdId": 0,
  "ExternalCustomerId": "string",
  "CustomerName": "string",
  "CustomerDocument": "string",
  "BankNumber": "string",
  "BankBranchNumber": "string",
  "BankAccountNumber": "string",
  "BankAccountType": "string",
  "BankAccountHolderName": "string",
  "BankAccountHolderDocument": "string",
  "CreatedDate": "2019-08-24T14:15:22Z",
  "Validated": true,
  "Blacklisted": true,
  "UpdatedDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|BankAccountId|integer(int32)|false|none|none|
|Pid|integer(int32)|false|none|none|
|ProdId|integer(int32)|false|none|none|
|ExternalCustomerId|string|false|none|none|
|CustomerName|string|false|none|none|
|CustomerDocument|string|false|none|none|
|BankNumber|string|false|none|none|
|BankBranchNumber|string|false|none|none|
|BankAccountNumber|string|false|none|none|
|BankAccountType|string|false|none|none|
|BankAccountHolderName|string|false|none|none|
|BankAccountHolderDocument|string|false|none|none|
|CreatedDate|string(date-time)|false|none|none|
|Validated|boolean|false|none|none|
|Blacklisted|boolean|false|none|none|
|UpdatedDate|string(date-time)|false|none|none|

<h2 id="tocS_NearbyPlaces">NearbyPlaces</h2>
<!-- backwards compatibility -->
<a id="schemanearbyplaces"></a>
<a id="schema_NearbyPlaces"></a>
<a id="tocSnearbyplaces"></a>
<a id="tocsnearbyplaces"></a>

```json
{
  "Results": [
    {
      "Geometry": {
        "Location": {
          "Lat": 0,
          "Lng": 0
        }
      },
      "Name": "string",
      "OpeningHours": {
        "open_now": true
      },
      "Vicinity": "string"
    }
  ],
  "Status": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Results|[[NearbyPlace](#schemanearbyplace)]|false|none|none|
|Status|string|false|none|none|

<h2 id="tocS_NearbyPlace">NearbyPlace</h2>
<!-- backwards compatibility -->
<a id="schemanearbyplace"></a>
<a id="schema_NearbyPlace"></a>
<a id="tocSnearbyplace"></a>
<a id="tocsnearbyplace"></a>

```json
{
  "Geometry": {
    "Location": {
      "Lat": 0,
      "Lng": 0
    }
  },
  "Name": "string",
  "OpeningHours": {
    "open_now": true
  },
  "Vicinity": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Geometry|[NearbyPlaceGeometry](#schemanearbyplacegeometry)|false|none|none|
|Name|string|false|none|none|
|OpeningHours|[NearbyPlaceOpeningHours](#schemanearbyplaceopeninghours)|false|none|none|
|Vicinity|string|false|none|none|

<h2 id="tocS_NearbyPlaceGeometry">NearbyPlaceGeometry</h2>
<!-- backwards compatibility -->
<a id="schemanearbyplacegeometry"></a>
<a id="schema_NearbyPlaceGeometry"></a>
<a id="tocSnearbyplacegeometry"></a>
<a id="tocsnearbyplacegeometry"></a>

```json
{
  "Location": {
    "Lat": 0,
    "Lng": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Location|[NearbyPlaceLocation](#schemanearbyplacelocation)|false|none|none|

<h2 id="tocS_NearbyPlaceLocation">NearbyPlaceLocation</h2>
<!-- backwards compatibility -->
<a id="schemanearbyplacelocation"></a>
<a id="schema_NearbyPlaceLocation"></a>
<a id="tocSnearbyplacelocation"></a>
<a id="tocsnearbyplacelocation"></a>

```json
{
  "Lat": 0,
  "Lng": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Lat|number(double)|false|none|none|
|Lng|number(double)|false|none|none|

<h2 id="tocS_NearbyPlaceOpeningHours">NearbyPlaceOpeningHours</h2>
<!-- backwards compatibility -->
<a id="schemanearbyplaceopeninghours"></a>
<a id="schema_NearbyPlaceOpeningHours"></a>
<a id="tocSnearbyplaceopeninghours"></a>
<a id="tocsnearbyplaceopeninghours"></a>

```json
{
  "open_now": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|open_now|boolean|false|none|none|

<h2 id="tocS_ListUsersBankAccountsRequest">ListUsersBankAccountsRequest</h2>
<!-- backwards compatibility -->
<a id="schemalistusersbankaccountsrequest"></a>
<a id="schema_ListUsersBankAccountsRequest"></a>
<a id="tocSlistusersbankaccountsrequest"></a>
<a id="tocslistusersbankaccountsrequest"></a>

```json
{
  "CustomerDocument": "string",
  "ExternalCustomerId": "string",
  "Pid": 0,
  "ProdId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CustomerDocument|string|false|none|none|
|ExternalCustomerId|string|false|none|none|

<h2 id="tocS_ListUsersBankAccountsReply">ListUsersBankAccountsReply</h2>
<!-- backwards compatibility -->
<a id="schemalistusersbankaccountsreply"></a>
<a id="schema_ListUsersBankAccountsReply"></a>
<a id="tocSlistusersbankaccountsreply"></a>
<a id="tocslistusersbankaccountsreply"></a>

```json
{
  "Result": [
    {
      "BankAccountId": 0,
      "Pid": 0,
      "ProdId": 0,
      "ExternalCustomerId": "string",
      "CustomerName": "string",
      "CustomerDocument": "string",
      "BankNumber": "string",
      "BankBranchNumber": "string",
      "BankAccountNumber": "string",
      "BankAccountType": "string",
      "BankAccountHolderName": "string",
      "BankAccountHolderDocument": "string",
      "CreatedDate": "2019-08-24T14:15:22Z",
      "Validated": true,
      "Blacklisted": true,
      "UpdatedDate": "2019-08-24T14:15:22Z"
    }
  ],
  "Success": true,
  "Message": "string",
  "StatusCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Result|[[UserBankAccount](#schemauserbankaccount)]|false|none|none|

<h2 id="tocS_GetNearbyBanksReply">GetNearbyBanksReply</h2>
<!-- backwards compatibility -->
<a id="schemagetnearbybanksreply"></a>
<a id="schema_GetNearbyBanksReply"></a>
<a id="tocSgetnearbybanksreply"></a>
<a id="tocsgetnearbybanksreply"></a>

```json
{
  "Result": {
    "Results": [
      {
        "Geometry": {
          "Location": {
            "Lat": 0,
            "Lng": 0
          }
        },
        "Name": "string",
        "OpeningHours": {
          "open_now": true
        },
        "Vicinity": "string"
      }
    ],
    "Status": "string"
  },
  "Success": true,
  "Message": "string",
  "StatusCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Result|[NearbyPlaces](#schemanearbyplaces)|false|none|none|

