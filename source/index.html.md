---
title: Appointments management API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers:
  - '<a href="https://docs.google.com/spreadsheets">API design</a>'
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="appointments-management-api">Appointments management API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Specification for appointment management service with notifications

Base URLs:

* <a href="https://api.bgenda.dmbarreiro.com/v1.0/">https://api.bgenda.dmbarreiro.com/v1.0/</a>

Email: <a href="mailto:david@dmbarreiro.com">David Martinez Barreiro</a> Web: <a href="https://www.dmbarreiro.com">David Martinez Barreiro</a> 
 License: All Rights Reserved

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **api_key**, in: header. 

- HTTP Authentication, scheme: basic 

- HTTP Authentication, scheme: bearer 

<h1 id="appointments-management-api-authentication">authentication</h1>

Authentication system management

## getToken

<a id="opIdgetToken"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/auth/login \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'api_key: API_KEY'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/auth/login HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'api_key':'API_KEY'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/auth/login',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "email": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'api_key':'API_KEY'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/auth/login',
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
  'api_key' => 'API_KEY'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/auth/login',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'api_key': 'API_KEY'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/auth/login', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/auth/login");
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
        "api_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/auth/login", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /auth/login`

*Returns JWT authentication token*

Returns JWT authentication token when succeding and an information message

> Body parameter

```json
{
  "email": "string",
  "password": "string"
}
```

<h3 id="gettoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Contains user e-mail and password|
|» email|body|string|true|none|
|» password|body|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "string",
  "token": "string"
}
```

<h3 id="gettoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets user token|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="gettoken-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|true|none|none|
|» token|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## invalidateToken

<a id="opIdinvalidateToken"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/auth/logout \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'api_key: API_KEY'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/auth/logout HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'api_key':'API_KEY'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/auth/logout',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "email": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'api_key':'API_KEY'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/auth/logout',
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
  'api_key' => 'API_KEY'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/auth/logout',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'api_key': 'API_KEY'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/auth/logout', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/auth/logout");
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
        "api_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/auth/logout", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /auth/logout`

*Invalidates JWT authentication token*

Invalidates JWT authentication token when succeding

> Body parameter

```json
{
  "email": "string",
  "password": "string"
}
```

<h3 id="invalidatetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Contains user e-mail and password|
|» email|body|string|true|none|
|» password|body|string|true|none|

> Example responses

> 204 Response

```json
{
  "message": "string"
}
```

<h3 id="invalidatetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Invalidates employee token|Inline|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="invalidatetoken-responseschema">Response Schema</h3>

Status Code **204**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="appointments-management-api-companies">companies</h1>

Companies using appointments service

## getCompanyById

<a id="opIdgetCompanyById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}`

*Returns single company information*

Returns company information identified by {id}. Requires administrator permissions.

<h3 id="getcompanybyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
{
  "company": {
    "active": true,
    "IANA_timezone": "Europe/Madrid",
    "locale": "es-ES",
    "name": "string",
    "notification_advance": 86400,
    "address": {
      "street": "string",
      "city": "string",
      "county": "string",
      "state": "string",
      "country": "string",
      "post_code": 0
    },
    "_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "message": "Element successfully found"
}
```

<h3 id="getcompanybyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific company|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Company not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanybyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» company|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|
|»»» active|boolean|false|none|none|
|»»» IANA_timezone|string|false|none|none|
|»»» locale|string|false|none|none|
|»»» name|string|true|none|none|
|»»» notification_advance|integer(int64)|false|none|none|
|»»» address|object|true|none|none|
|»»»» street|string|true|none|none|
|»»»» city|string|true|none|none|
|»»»» county|string|false|none|none|
|»»»» state|string|false|none|none|
|»»»» country|string|true|none|none|
|»»»» post_code|integer|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|object|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» created_at|string(date-time)|true|none|none|
|»»»» updated_at|string(date-time)|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateCompanyById

<a id="opIdupdateCompanyById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.bgenda.dmbarreiro.com/v1.0/companies/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.bgenda.dmbarreiro.com/v1.0/companies/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  },
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /companies/{id}`

*Updates company information*

Updates company information data identified by {id} returning no information. Requires administrator permissions.

> Body parameter

```json
{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  },
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z"
}
```

<h3 id="updatecompanybyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|
|body|body|[RegisteredCompany](#schemaregisteredcompany)|true|Contains company information to be updated on the record, must contain all company requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string",
  "status": 0
}
```

<h3 id="updatecompanybyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Company not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getCompanyEmployees

<a id="opIdgetCompanyEmployees"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/employees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}/employees`

*Returns company employee data*

Returns all company employees data. Needs add_employee permission.

<h3 id="getcompanyemployees-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
[
  {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  }
]
```

<h3 id="getcompanyemployees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company employee data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanyemployees-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|
|»» active|boolean|false|none|none|
|»» password|string|true|none|none|
|»» name|string|true|none|none|
|»» surname|string|true|none|none|
|»» email|string|true|none|none|
|»» phone_number|string|false|none|none|
|»» privileges|object|false|none|none|
|»»» add_employee|boolean|false|none|none|
|»»» update_client|boolean|false|none|none|
|»»» update_schedule|boolean|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» _id|string|true|none|none|
|»»» company_id|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» last_modified_by|string|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getCompanyClients

<a id="opIdgetCompanyClients"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/companies/{id}/clients", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}/clients`

*Returns company client data*

Returns all company clients data. Requires update_client permission.

<h3 id="getcompanyclients-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
[
  {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  }
]
```

<h3 id="getcompanyclients-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array with client information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanyclients-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»» active|boolean|false|none|none|
|»» name|string|true|none|none|
|»» surname|string|true|none|none|
|»» email|string|true|none|none|
|»» phone_number|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» _id|string|true|none|none|
|»» company_added|string|true|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» updated_at|string(date-time)|true|none|none|
|»» last_modified_by|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getCompanies

<a id="opIdgetCompanies"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/companies \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/companies HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/companies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/companies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies`

*Returns information from all companies*

Returns an array with information from each company. Needs administrator permissions.

> Example responses

> 200 Response

```json
[
  {
    "active": true,
    "IANA_timezone": "Europe/Madrid",
    "locale": "es-ES",
    "name": "string",
    "notification_advance": 86400,
    "address": {
      "street": "string",
      "city": "string",
      "county": "string",
      "state": "string",
      "country": "string",
      "post_code": 0
    },
    "_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z"
  }
]
```

<h3 id="getcompanies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanies-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|
|»» active|boolean|false|none|none|
|»» IANA_timezone|string|false|none|none|
|»» locale|string|false|none|none|
|»» name|string|true|none|none|
|»» notification_advance|integer(int64)|false|none|none|
|»» address|object|true|none|none|
|»»» street|string|true|none|none|
|»»» city|string|true|none|none|
|»»» county|string|false|none|none|
|»»» state|string|false|none|none|
|»»» country|string|true|none|none|
|»»» post_code|integer|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» _id|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createCompany

<a id="opIdcreateCompany"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/companies \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/companies HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/companies',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/companies',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/companies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/companies");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/companies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /companies`

*Creates new company*

Creates new company returning no information. Needs administrator permissions.

> Body parameter

```json
{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}
```

<h3 id="createcompany-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicCompany](#schemabasiccompany)|true|Contains company information to be added to the record|

> Example responses

> 201 Response

```json
{
  "company": {
    "active": true,
    "IANA_timezone": "Europe/Madrid",
    "locale": "es-ES",
    "name": "string",
    "notification_advance": 86400,
    "address": {
      "street": "string",
      "city": "string",
      "county": "string",
      "state": "string",
      "country": "string",
      "post_code": 0
    },
    "_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "message": "Element successfully created"
}
```

<h3 id="createcompany-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="createcompany-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» company|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|
|»»» active|boolean|false|none|none|
|»»» IANA_timezone|string|false|none|none|
|»»» locale|string|false|none|none|
|»»» name|string|true|none|none|
|»»» notification_advance|integer(int64)|false|none|none|
|»»» address|object|true|none|none|
|»»»» street|string|true|none|none|
|»»»» city|string|true|none|none|
|»»»» county|string|false|none|none|
|»»»» state|string|false|none|none|
|»»»» country|string|true|none|none|
|»»»» post_code|integer|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|object|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» created_at|string(date-time)|true|none|none|
|»»»» updated_at|string(date-time)|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="appointments-management-api-employees">employees</h1>

Companies employees

## getEmployeeById

<a id="opIdgetEmployeeById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/employees/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/employees/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /employees/{id}`

*Returns single employee data*

Returns employee data identified by {id}

<h3 id="getemployeebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Employee id|

> Example responses

> 200 Response

```json
{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  },
  "_id": "string",
  "company_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string",
  "updated_at": "2019-09-22T22:56:48Z"
}
```

<h3 id="getemployeebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific employee|[RegisteredEmployee](#schemaregisteredemployee)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Employee not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateEmployeeById

<a id="opIdupdateEmployeeById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.bgenda.dmbarreiro.com/v1.0/employees/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.bgenda.dmbarreiro.com/v1.0/employees/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  },
  "_id": "string",
  "company_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string",
  "updated_at": "2019-09-22T22:56:48Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.bgenda.dmbarreiro.com/v1.0/employees/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /employees/{id}`

*Updates employee information*

Updates employee data identified by {id} returning no information. Needs add_employee user permission.

> Body parameter

```json
{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  },
  "_id": "string",
  "company_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string",
  "updated_at": "2019-09-22T22:56:48Z"
}
```

<h3 id="updateemployeebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[RegisteredEmployee](#schemaregisteredemployee)|true|Contains employee information to be updated on the record, must contain all employee requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string",
  "status": 0
}
```

<h3 id="updateemployeebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Employee not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createEmployee

<a id="opIdcreateEmployee"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/employees \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/employees HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/employees',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/employees',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/employees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/employees");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/employees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /employees`

*Creates new employee*

Creates new employee returning no information.  Needs add_employee user permission.

> Body parameter

```json
{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  }
}
```

<h3 id="createemployee-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicEmployee](#schemabasicemployee)|true|Contains employee information to be added to the record|

> Example responses

> 201 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="createemployee-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="createemployee-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|number|false|none|none|
|» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="appointments-management-api-clients">clients</h1>

Companies clients

## getClientById

<a id="opIdgetClientById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/clients/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/clients/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}`

*Returns single client data*

Returns client data identified by {id}.

<h3 id="getclientbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|

> Example responses

> 200 Response

```json
{
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "message": "Element successfully found"
}
```

<h3 id="getclientbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific client|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Required request parameters are missing or are incorrect|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getclientbyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» client|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»»» active|boolean|false|none|none|
|»»» name|string|true|none|none|
|»»» surname|string|true|none|none|
|»»» email|string|true|none|none|
|»»» phone_number|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» _id|string|true|none|none|
|»»» company_added|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|
|»»» last_modified_by|string|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateClientById

<a id="opIdupdateClientById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.bgenda.dmbarreiro.com/v1.0/clients/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.bgenda.dmbarreiro.com/v1.0/clients/{id} HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "_id": "string",
  "company_added": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /clients/{id}`

*Updates client information*

Updates client data identified by {id} returning no information. Requires update_client permission.

> Body parameter

```json
{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "_id": "string",
  "company_added": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}
```

<h3 id="updateclientbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[RegisteredClient](#schemaregisteredclient)|true|Contains client information to be updated on the record, must contain all client requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string",
  "status": 0
}
```

<h3 id="updateclientbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getClientAppointment

<a id="opIdgetClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}/appointments`

*Returns client appointments or single appointment information*

Returns all client appointments or single appointment information information data. Client information is specified by path id and appointment information is provided by optional query parameter appointment_id.

<h3 id="getclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|from|query|string(date-time)|false|Filter out appointments starting before this string date|
|to|query|string(date-time)|false|Filter out appointments ending after this string date|

> Example responses

> 200 Response

```json
{
  "message": "Element successfully found",
  "appointments": [
    {
      "company_id": "string",
      "client": {
        "active": true,
        "name": "string",
        "surname": "string",
        "email": "string",
        "phone_number": "string",
        "_id": "string",
        "company_added": "string",
        "created_at": "2019-09-22T22:56:48Z",
        "updated_at": "2019-09-22T22:56:48Z",
        "last_modified_by": "string"
      },
      "employee": {
        "active": true,
        "password": "string",
        "name": "string",
        "surname": "string",
        "email": "string",
        "phone_number": "string",
        "privileges": {
          "add_employee": false,
          "update_client": false,
          "update_schedule": false
        },
        "_id": "string",
        "company_id": "string",
        "created_at": "2019-09-22T22:56:48Z",
        "last_modified_by": "string",
        "updated_at": "2019-09-22T22:56:48Z"
      },
      "start_date": "2019-09-22T22:56:48Z",
      "end_date": "2019-09-22T22:56:48Z",
      "_id": "string",
      "created_at": "2019-09-22T22:56:48Z",
      "updated_at": "2019-09-22T22:56:48Z",
      "last_modified_by": "string"
    }
  ]
}
```

<h3 id="getclientappointment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets array of with information of all client appointments or single appointment information if ?appointment_id is added to request. Client identified by {id}|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Appointments or appointment not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getclientappointment-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» appointments|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicAppointment](#schemabasicappointment)|false|none|none|
|»»» company_id|string|true|none|none|
|»»» client|any|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»»»»» active|boolean|false|none|none|
|»»»»» name|string|true|none|none|
|»»»»» surname|string|true|none|none|
|»»»»» email|string|true|none|none|
|»»»»» phone_number|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|object|false|none|none|
|»»»»» _id|string|true|none|none|
|»»»»» company_added|string|true|none|none|
|»»»»» created_at|string(date-time)|true|none|none|
|»»»»» updated_at|string(date-time)|true|none|none|
|»»»»» last_modified_by|string|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» employee|any|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» *anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|
|»»»»»» active|boolean|false|none|none|
|»»»»»» password|string|true|none|none|
|»»»»»» name|string|true|none|none|
|»»»»»» surname|string|true|none|none|
|»»»»»» email|string|true|none|none|
|»»»»»» phone_number|string|false|none|none|
|»»»»»» privileges|object|false|none|none|
|»»»»»»» add_employee|boolean|false|none|none|
|»»»»»»» update_client|boolean|false|none|none|
|»»»»»»» update_schedule|boolean|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» *anonymous*|object|false|none|none|
|»»»»»»» _id|string|true|none|none|
|»»»»»»» company_id|string|true|none|none|
|»»»»»»» created_at|string(date-time)|true|none|none|
|»»»»»»» last_modified_by|string|true|none|none|
|»»»»»»» updated_at|string(date-time)|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» start_date|string(date-time)|true|none|none|
|»»»»»» end_date|string(date-time)|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» *anonymous*|object|false|none|none|
|»»»»»» _id|string|true|none|none|
|»»»»»» created_at|string(date-time)|true|none|none|
|»»»»»» updated_at|string(date-time)|true|none|none|
|»»»»»» last_modified_by|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateClientAppointment

<a id="opIdupdateClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments?appointment_id=string \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments?appointment_id=string HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  method: 'put',
  data: '?appointment_id=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z",
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments?appointment_id=string',
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

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  params: {
  'appointment_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments', params={
  'appointment_id': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments?appointment_id=string");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /clients/{id}/appointments`

*Updates appointment information*

Updates appointment data for client identified by {id} and appointment identified by ?appointment_id returning no information. Requires update_schedule permission.

> Body parameter

```json
{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z",
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}
```

<h3 id="updateclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|appointment_id|query|string|true|Appointment resource identified|
|body|body|[RegisteredAppointment](#schemaregisteredappointment)|true|Contains appointment information to be updated on the record, must contain all appointment requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string",
  "status": 0
}
```

<h3 id="updateclientappointment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Appointment not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createClientAppointment

<a id="opIdcreateClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /clients/{id}/appointments`

*Creates new appointment for client*

Creates new appointment returning new appointment information. Client identified by {id}.

> Body parameter

```json
{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z"
}
```

<h3 id="createclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[BasicAppointment](#schemabasicappointment)|true|Contains appointment information to be added to the record|

> Example responses

> 201 Response

```json
{
  "appointment": {
    "company_id": "string",
    "client": {
      "active": true,
      "name": "string",
      "surname": "string",
      "email": "string",
      "phone_number": "string",
      "_id": "string",
      "company_added": "string",
      "created_at": "2019-09-22T22:56:48Z",
      "updated_at": "2019-09-22T22:56:48Z",
      "last_modified_by": "string"
    },
    "employee": {
      "active": true,
      "password": "string",
      "name": "string",
      "surname": "string",
      "email": "string",
      "phone_number": "string",
      "privileges": {
        "add_employee": false,
        "update_client": false,
        "update_schedule": false
      },
      "_id": "string",
      "company_id": "string",
      "created_at": "2019-09-22T22:56:48Z",
      "last_modified_by": "string",
      "updated_at": "2019-09-22T22:56:48Z"
    },
    "start_date": "2019-09-22T22:56:48Z",
    "end_date": "2019-09-22T22:56:48Z",
    "_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "message": "Element successfully created"
}
```

<h3 id="createclientappointment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="createclientappointment-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» appointment|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicAppointment](#schemabasicappointment)|false|none|none|
|»»» company_id|string|true|none|none|
|»»» client|any|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»»»»» active|boolean|false|none|none|
|»»»»» name|string|true|none|none|
|»»»»» surname|string|true|none|none|
|»»»»» email|string|true|none|none|
|»»»»» phone_number|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|object|false|none|none|
|»»»»» _id|string|true|none|none|
|»»»»» company_added|string|true|none|none|
|»»»»» created_at|string(date-time)|true|none|none|
|»»»»» updated_at|string(date-time)|true|none|none|
|»»»»» last_modified_by|string|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» employee|any|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» *anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|
|»»»»»» active|boolean|false|none|none|
|»»»»»» password|string|true|none|none|
|»»»»»» name|string|true|none|none|
|»»»»»» surname|string|true|none|none|
|»»»»»» email|string|true|none|none|
|»»»»»» phone_number|string|false|none|none|
|»»»»»» privileges|object|false|none|none|
|»»»»»»» add_employee|boolean|false|none|none|
|»»»»»»» update_client|boolean|false|none|none|
|»»»»»»» update_schedule|boolean|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» *anonymous*|object|false|none|none|
|»»»»»»» _id|string|true|none|none|
|»»»»»»» company_id|string|true|none|none|
|»»»»»»» created_at|string(date-time)|true|none|none|
|»»»»»»» last_modified_by|string|true|none|none|
|»»»»»»» updated_at|string(date-time)|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» start_date|string(date-time)|true|none|none|
|»»»»»» end_date|string(date-time)|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» *anonymous*|object|false|none|none|
|»»»»»» _id|string|true|none|none|
|»»»»»» created_at|string(date-time)|true|none|none|
|»»»»»» updated_at|string(date-time)|true|none|none|
|»»»»»» last_modified_by|string|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createClient

<a id="opIdcreateClient"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://api.bgenda.dmbarreiro.com/v1.0/clients \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.bgenda.dmbarreiro.com/v1.0/clients HTTP/1.1
Host: api.bgenda.dmbarreiro.com
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.bgenda.dmbarreiro.com/v1.0/clients',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.bgenda.dmbarreiro.com/v1.0/clients',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.bgenda.dmbarreiro.com/v1.0/clients',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.bgenda.dmbarreiro.com/v1.0/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.bgenda.dmbarreiro.com/v1.0/clients");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.bgenda.dmbarreiro.com/v1.0/clients", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /clients`

*Creates new client*

Creates new client returning new client information.

> Body parameter

```json
{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string"
}
```

<h3 id="createclient-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicClient](#schemabasicclient)|true|Contains client information to be added to the record|

> Example responses

> 201 Response

```json
{
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "message": "Element successfully created"
}
```

<h3 id="createclient-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="createclient-responseschema">Response Schema</h3>

Status Code **201**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» client|any|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»»» active|boolean|false|none|none|
|»»» name|string|true|none|none|
|»»» surname|string|true|none|none|
|»»» email|string|true|none|none|
|»»» phone_number|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» _id|string|true|none|none|
|»»» company_added|string|true|none|none|
|»»» created_at|string(date-time)|true|none|none|
|»»» updated_at|string(date-time)|true|none|none|
|»»» last_modified_by|string|true|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» message|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

# Schemas

<h2 id="tocSgeneralerror">GeneralError</h2>

<a id="schemageneralerror"></a>

```json
{
  "message": "string",
  "status": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|
|status|number|true|none|none|

<h2 id="tocSregisteredemployee">RegisteredEmployee</h2>

<a id="schemaregisteredemployee"></a>

```json
{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  },
  "_id": "string",
  "company_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string",
  "updated_at": "2019-09-22T22:56:48Z"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» _id|string|true|none|none|
|» company_id|string|true|none|none|
|» created_at|string(date-time)|true|none|none|
|» last_modified_by|string|true|none|none|
|» updated_at|string(date-time)|true|none|none|

<h2 id="tocSbasicemployee">BasicEmployee</h2>

<a id="schemabasicemployee"></a>

```json
{
  "active": true,
  "password": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "privileges": {
    "add_employee": false,
    "update_client": false,
    "update_schedule": false
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|false|none|none|
|password|string|true|none|none|
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone_number|string|false|none|none|
|privileges|object|false|none|none|
|» add_employee|boolean|false|none|none|
|» update_client|boolean|false|none|none|
|» update_schedule|boolean|false|none|none|

<h2 id="tocSregisteredclient">RegisteredClient</h2>

<a id="schemaregisteredclient"></a>

```json
{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string",
  "_id": "string",
  "company_added": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicClient](#schemabasicclient)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» _id|string|true|none|none|
|» company_added|string|true|none|none|
|» created_at|string(date-time)|true|none|none|
|» updated_at|string(date-time)|true|none|none|
|» last_modified_by|string|true|none|none|

<h2 id="tocSbasicclient">BasicClient</h2>

<a id="schemabasicclient"></a>

```json
{
  "active": true,
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone_number": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|false|none|none|
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone_number|string|false|none|none|

<h2 id="tocSregisteredcompany">RegisteredCompany</h2>

<a id="schemaregisteredcompany"></a>

```json
{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  },
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» _id|string|true|none|none|
|» created_at|string(date-time)|true|none|none|
|» updated_at|string(date-time)|true|none|none|

<h2 id="tocSbasiccompany">BasicCompany</h2>

<a id="schemabasiccompany"></a>

```json
{
  "active": true,
  "IANA_timezone": "Europe/Madrid",
  "locale": "es-ES",
  "name": "string",
  "notification_advance": 86400,
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|false|none|none|
|IANA_timezone|string|false|none|none|
|locale|string|false|none|none|
|name|string|true|none|none|
|notification_advance|integer(int64)|false|none|none|
|address|object|true|none|none|
|» street|string|true|none|none|
|» city|string|true|none|none|
|» county|string|false|none|none|
|» state|string|false|none|none|
|» country|string|true|none|none|
|» post_code|integer|true|none|none|

<h2 id="tocSregisteredappointment">RegisteredAppointment</h2>

<a id="schemaregisteredappointment"></a>

```json
{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z",
  "_id": "string",
  "created_at": "2019-09-22T22:56:48Z",
  "updated_at": "2019-09-22T22:56:48Z",
  "last_modified_by": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicAppointment](#schemabasicappointment)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» _id|string|true|none|none|
|» created_at|string(date-time)|true|none|none|
|» updated_at|string(date-time)|true|none|none|
|» last_modified_by|string|true|none|none|

<h2 id="tocSbasicappointment">BasicAppointment</h2>

<a id="schemabasicappointment"></a>

```json
{
  "company_id": "string",
  "client": {
    "active": true,
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "_id": "string",
    "company_added": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "updated_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string"
  },
  "employee": {
    "active": true,
    "password": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone_number": "string",
    "privileges": {
      "add_employee": false,
      "update_client": false,
      "update_schedule": false
    },
    "_id": "string",
    "company_id": "string",
    "created_at": "2019-09-22T22:56:48Z",
    "last_modified_by": "string",
    "updated_at": "2019-09-22T22:56:48Z"
  },
  "start_date": "2019-09-22T22:56:48Z",
  "end_date": "2019-09-22T22:56:48Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|company_id|string|true|none|none|
|client|[RegisteredClient](#schemaregisteredclient)|true|none|none|
|employee|[RegisteredEmployee](#schemaregisteredemployee)|true|none|none|
|start_date|string(date-time)|true|none|none|
|end_date|string(date-time)|true|none|none|

