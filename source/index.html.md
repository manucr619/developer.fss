---
title: FSS Acquiring - API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - Go Lang
  - PHP
  - Java
  - python

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://www.fsstech.com/node/1'>Documentation Powered by FSS</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction  

Welcome to the FSS Aquiring Platform You can use our API to access FSS API endpoints, which can POST information on various Payments through Payment Gateway , POSability.

We have language bindings in Shell, PHP, Python, and Java! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created by [ Financial Software and Systems - Payment Gateway ](https://www.fsstech.com/fssacquiring/fsspaymentgateway).

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

FSS Acquiring platform uses API keys to allow access to the API. You can register a new Merchant API key at our [developer portal](http://developers.fssnet.com).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>

# Payments

## Hosted Payment API

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953')
api.Merchants.POST
```

```python
import kittn

api = kittn.authorize('WAlYxI97110109010953')
api.Merchants.POST()
```

```shell
curl "http://example.com/api/Merchants"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('WAlYxI97110109010953');
let Merchants = api.Merchants.POST();
```

> Request : JSON structured like this:

```json
[
  {
  "action": 1,
  "tranportalId": 813784512,
  "shipToCountryCd": 356,
  "password": "Test@123",
  "amount": 36,
  "customerId": 201502889575739,
  "merchantResponseURL": "http://fss.product.com/Merchant_Demo_Rest_Api/jsp/fss/HostedPaymentResult.jsp",
  "merchantErrorURL": "http://fss.product.com/Merchant_Demo_Rest_Api/jsp/fss/HostedPaymentResult.jsp",
  "merchantRefId": 1529707420,
  "udf1": "string",
  "udf2": "string",
  "udf3": "string",
  "udf4": "string",
  "udf5": "string",
  "udf6": "string",
  "udf7": "string",
  "udf8": "string",
  "udf9": "string",
  "udf10": "string",
  "udf11": "string",
  "udf12": "string",
  "udf13": "string",
  "udf14": "string",
  "udf15": "string",
  "currencyCode": 356,
  "language": "USA",
  "shipToPostalcd": 4758845,
  "shipToLastName": "Test",
  "shipToFirstName": "Testing",
  "shipToAddress": "chennai",
  "shipToPhnNum": 7548758433,
  "signature": "37e3c831c2d59bb7b68a067c467b9abded7670cd"
}

]
```



> The above command returns JSON structured like this:

```json
[
  {
  "result": "string"
}
]
```

This endpoint retrieves all Merchants.

### HTTP Request

`POST https://manucr619-eval-test.apigee.net/pghosted`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
action | true | If set to true, the result will also include datas.
tranportalId | true | If set to false, the result will include tranportal ID that have already been Registered.
shipToCountryCd | true | If set to false, the result will include Country Code that have already been Registered.
password | true | For auth basic password to Login
amount | true | Transaction Amount

<aside class="success">
Remember — All  API Should include the Bank Unique Key and Merchant Key  
</aside>

## Supported Payments API

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953')
api.Merchants.POST(2)
```

```python
import kittn

api = kittn.authorize('WAlYxI97110109010953')
api.Merchants.POST(2)
```

```shell
curl "http://example.com/api/Merchants/2"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('WAlYxI97110109010953');
let max = api.Merchants.POST(2);
```

> Request : JSON structured like this:

```json
{
  "paymentid": 813202017610296300,
  "paRes": "string",
  "tranportalId": 81398653223,
  "password": "Test@123",
  "signature": "13984d73085bf060bb27b09badb2a5de6b242f50"
}
```



> The above command returns JSON structured like this:

```json
{{
  "acsSignedContent": "string",
  "acsTranID": "string",
  "amt": "string",
  "auth": "string",
  "authDataEncryptKey": "string",
  "authDataEncryptMandatory": "string",
  "authDataEncryptType": "string",
  "authDataLabel": "string",
  "authDataLength": "string",
  "authDataName": "string",
  "authDataPrompt": "string",
  "authDataType": "string",
  "authRespCode": "string",
  "avr": "string",
  "cReq": "string",
  "cardType": "string",
  "cardbalance": "string",
  "custid": "string",
  "dsTranID": "string",
  "eci": "string",
  "errorCode": "string",
  "errorText": "string",
  "error_code_tag": "string",
  "error_service_tag": "string",
  "error_text": "string",
  "ivrFlag": "string",
  "pareq": "string",
  "payid": "string",
  "paymentid": "string",
  "postdate": "string",
  "ref": "string",
  "result": "string",
  "threeDSServerTranID": "string",
  "threeDSSessionData": "string",
  "trackid": "string",
  "tranStatus": "string",
  "tranid": "string",
  "udf1": "string",
  "udf10": "string",
  "udf11": "string",
  "udf12": "string",
  "udf13": "string",
  "udf14": "string",
  "udf15": "string",
  "udf2": "string",
  "udf3": "string",
  "udf4": "string",
  "udf5": "string",
  "udf6": "string",
  "udf7": "string",
  "udf8": "string",
  "udf9": "string",
  "url": "string"
}
```



This endpoint retrieves a specific Supoorted API for Payment.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`POST https://manucr619-eval-test.apigee.net/pghosted<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Merchant to retrieve

## Tran Portal API

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953')
api.Merchants.delete(2)
```

```python
import kittn

api = kittn.authorize('WAlYxI97110109010953')
api.Merchants.delete(2)
```

```shell
curl "http://example.com/api/Merchants/2"
  -X DELETE
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('WAlYxI97110109010953');
let max = api.Merchants.delete(2);
```

> Request : JSON structured like this:

```json
{
  "action": 1,
  "card": 5360192000000271,
  "cvv2": 123,
  "currency": 356,
  "expyear": 2014,
  "expmonth": 12,
  "expday": 15,
  "langid": "USA",
  "member": "Test",
  "amt": 90,
  "trackid": 5695640238739715000,
  "currencycode": 356,
  "custid": 5360192000000271,
  "card_PostalCd": 7859798,
  "card_Address": "chennai",
  "card_FirstName": "test",
  "card_LastName": "name",
  "card_Phn_Num": 8875498856,
  "ship_To_Postalcd": 4758845,
  "ship_To_Address": "chennai",
  "ship_To_FirstName": "Testing",
  "ship_To_LastName": "Tes",
  "ship_To_Phn_Num": 7548758433,
  "ship_To_CountryCd": 356,
  "cust_email": "test@gmail.com",
  "id": 81398653223,
  "password": "Test@123",
  "errorURL": "http://fss.product.com/Merchant_Demo_Rest_Api/jsp/fss/TranPipeResult.jsp",
  "responseURL": "http://fss.product.com/Merchant_Demo_Rest_Api/jsp/fss/TranPipeResult.jsp",
  "udf1": "string",
  "udf2": "string",
  "udf3": "string",
  "udf4": "string",
  "udf5": "string",
  "udf6": "string",
  "udf7": "string",
  "udf8": "string",
  "udf9": "string",
  "udf10": "string",
  "udf11": "string",
  "udf12": "string",
  "udf13": "string",
  "udf14": "string",
  "udf15": "string",
  "signature": "string"
}
```

> The above command returns JSON structured like this:

```json
{
  "acsSignedContent": "string",
  "acsTranID": "string",
  "amt": "string",
  "auth": "string",
  "authDataEncryptKey": "string",
  "authDataEncryptMandatory": "string",
  "authDataEncryptType": "string",
  "authDataLabel": "string",
  "authDataLength": "string",
  "authDataName": "string",
  "authDataPrompt": "string",
  "authDataType": "string",
  "authRespCode": "string",
  "avr": "string",
  "cReq": "string",
  "cardType": "string",
  "cardbalance": "string",
  "custid": "string",
  "dsTranID": "string",
  "eci": "string",
  "errorCode": "string",
  "errorText": "string",
  "error_code_tag": "string",
  "error_service_tag": "string",
  "error_text": "string",
  "ivrFlag": "string",
  "pareq": "string",
  "payid": "string",
  "paymentid": "string",
  "postdate": "string",
  "ref": "string",
  "result": "string",
  "threeDSServerTranID": "string",
  "threeDSSessionData": "string",
  "trackid": "string",
  "tranStatus": "string",
  "tranid": "string",
  "udf1": "string",
  "udf10": "string",
  "udf11": "string",
  "udf12": "string",
  "udf13": "string",
  "udf14": "string",
  "udf15": "string",
  "udf2": "string",
  "udf3": "string",
  "udf4": "string",
  "udf5": "string",
  "udf6": "string",
  "udf7": "string",
  "udf8": "string",
  "udf9": "string",
  "url": "string"
}
```

This endpoint deletes a specific Merchant.

### HTTP Request

`DELETE https://manucr619-eval-test.apigee.net/pghosted`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Merchant to delete


# Merchant


## Aggregator Onboarding


> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Onboarding Aggregator API is used to onboard Aggregator by passing aggregator details like Aggregator Name, Address, Aggregator Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>





## Merchant Onboarding


> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Onboarding Aggregator API is used to onboard Aggregator by passing aggregator details like Aggregator Name, Address, Aggregator Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>



## Store Onboarding


> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Onboarding Aggregator API is used to onboard Aggregator by passing aggregator details like Aggregator Name, Address, Aggregator Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>



## Terminal Onboarding


> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Terminal Onboarding API is used to onboard terminal by passing aggregator details like terminal Name, IP, Device Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>




## Account Linking



> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Account Linking API is used to Link Accounts by passing merchant details like Aggregator Name, Address, Aggregator Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>




## Account Posting



> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('WAlYxI97110109010953 ')
```

```java
import kittn

api = kittn.authorize('WAlYxI97110109010953')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: WAlYxI97110109010953"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('');
```



> Request : JSON structured like this:

```json
{
 "header": {
    "instId": "602",
    "requestId": "API_14948",
    "apiType" : "AGGR",
    "srcAppType" : "WEB"    
  },
    "body": {
    "aggregators": [
{
    "agreementDate" : "2020-08-25",
    "aggregatorCode": "24082095",
    "aggreagatorName": "AmazonAlexa",
	"aggregatorAddress1": "1st Floor Kalpataru Prime IT Park",
	"aggregatorAddress2": "Wagle Industrial Estate",
        "aggregatorAddress3": "Thane",
        "aggregatorAddress4": "West",
	"countryName": "India",
    "cityName": "mumbai",
    "stateName" : "MAHARASHTRA",
	 "emailId": "bristo123@gmail.com",
	 "postalCode": "410206",
	 "panNumber": "789654123a",
	 "salesOrgId": "1243625369t8a",
    "subMerchantId": "09988",
   "merchantAggregator": "Y",     
    "recordNumber": "1",
    "recordType": "1",    
     "visaFlag" : "1",   
"marketIndicatorVisa" : "P",
"visaPaymentFacilitatorID" : "12345",
   "independentSalesOrganizationIndcMastercard" : "1",
    "mastercardPaymentFacilitatorID" : "M1345"
  }
  		  ]
  	}
}

```



> The above command returns JSON structured like this:

```json
{
    "header": {
        "requestId": "API_14948",
        "instId": "602",
        "apiType": "AGGR",
        "srcAppType": "WEB",
        "status": "SUCCESS",
        "errorDesc": ""
    },
    "body": {
        "totalSuccessCount": 1,
        "totalFailureCount": 0,
        "totalCount": 1,
        "response": [
            {
                "aggregatorCode": "24082095",
                "refNo": "1",
                "status": "SUCCESS",
                "errDes": [
                    ""
                ]
            }
        ]
    }
}
```

> Make sure to replace `WAlYxI97110109010953` with your API key.

Account Posting API is used to onboard account by passing aggregator details like Aggregator Name, Address, Aggregator Code etc.


`Authorization: WAlYxI97110109010953`

<aside class="notice">
You must replace <code>WAlYxI97110109010953</code> with your personal API key.
</aside>
