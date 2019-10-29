---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

EWM Electronic World Money is an open prepaid card platform that enables customers to create their own products that need prepaid card capabilities into their systems, apps and workflows.

Customers connect to EWM platform via organized HTTP-based REST APIs that use OAuth 2.0. standard for authorization.

Our platform is purely an API platform that you can easily and quickly integrate to your business.

JSON is returned by all APIs responses, requests and errors in order to make your life easier.

We have a sandbox environment and a production environment available. There are therefore 2 different keys to be used for both environments as there is no switch for changing between the environments. Therefore, requests made on sandbox environment will never have any financial impact.

# Get started

Get your sandbox key to play with our APIs for free, without any limitation.
<aside class="notice">
mailto:ewm@ewm.cards
</aside>

<aside class="notice">
Sandbox Base URL : https://demo-api.worldcurrency.cards
</aside>

Get your production key to connect our FX capabilities to your systems
<aside class="notice">
Production Base URL : https://api.worldcurrency.cards
</aside>


<div class="postman-run-button"
data-postman-action="collection/import"
data-postman-var-1="3b7a532dfdf85442bf8e"></div>
<script type="text/javascript">
  (function (p,o,s,t,m,a,n) {
    !p[s] && (p[s] = function () { (p[t] || (p[t] = [])).push(arguments); });
    !o.getElementById(s+t) && o.getElementsByTagName("head")[0].appendChild((
      (n = o.createElement("script")),
      (n.id = s+t), (n.async = 1), (n.src = m), n
    ));
  }(window, document, "_pm", "PostmanRunObject", "https://run.pstmn.io/button.js"));
</script>

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: bearer jwttoken"
```


> Make sure to replace `jwttoken` with your API key.

EWM expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: bearer jwttoken`

<aside class="notice">
You must replace <code>jwttoken</code> with your personal API key.
</aside>


# Manage funding accounts

## Search Tenants 



```shell
curl "BaseUrl + /api/v1/tenants/"
  -H "Authorization: bearer jwttoken"
```


> The above command returns below response

```JSON
{
  "content": [
    {
      "id": "string",
      "name": "string",
      "status": "string",
      "companyKey": "string",
      "domainName": "string",
      "themeCss": "string",
      "logoUrl": "string",
      "companyLegalName": "string",
      "companyTradingName": "string",
      "kyb": "string",
      "preferredLanguage": "string",
      "passwordRegex": "string",
      "businessAddressLine1": "string",
      "businessAddressLine2": "string",
      "businessZipcode": "string",
      "businessCity": "string",
      "businessCountry": "string",
      "phoneNumber": "string",
      "description": "string",
      "verificationProcess": "string",
      "cardProgramTypes": [
        "string"
      ],
      "photoOfInCorporateCerfUrl": "string",
      "photoOfGoodStandingCerfUrl": "string",
      "shippingAddresses": [
        {
          "addressLine1": "string",
          "addressLine2": "string",
          "city": "string",
          "country": "string",
          "emailAddress": "string",
          "firstName": "string",
          "id": "string",
          "isDefault": true,
          "lastName": "string",
          "nickName": "string",
          "phoneNumber": "string",
          "state": "string",
          "zipCode": "string"
        }
      ],
      "logo": {
        "fileName": "string",
        "removed": true,
        "data": "string",
        "url": "string",
        "isRemoved": true
      },
      "photoOfInCorporateCerf": {
        "fileName": "string",
        "removed": true,
        "data": "string",
        "url": "string",
        "isRemoved": true
      },
      "photoOfGoodStandingCerf": {
        "fileName": "string",
        "removed": true,
        "data": "string",
        "url": "string",
        "isRemoved": true
      },
      "documents": [
        {
          "fileName": "string",
          "removed": true,
          "data": "string",
          "url": "string",
          "isRemoved": true
        }
      ],
      "prefundingAccounts": [
        {
          "tenantId": "string",
          "currency": "string",
          "balance": 0,
          "reference": "string"
        }
      ],
      "activePrefundingAccounts": [
        "string"
      ],
      "cardPrograms": [
        {
          "commission": 0,
          "commissionType": "PROFIT_SHARE",
          "creationTime": "2019-04-24T06:22:55.002Z",
          "currency": "string",
          "deleted": true,
          "externalCardProgramCurrencies": "string",
          "externalCardProgramId": "string",
          "id": "string",
          "lastUpdatedTime": "2019-04-24T06:22:55.002Z",
          "name": "string",
          "tenantId": "string",
          "tenantName": "string",
          "termAndCondition": {
            "description": "string",
            "id": "string",
            "name": "string",
            "url": "string"
          }
        }
      ],
      "numberOfActiveCardholders": 0,
      "numberOfPendingCardholders": 0,
      "contacts": [
        {
          "birthDate": "2019-04-24",
          "emailAddress": "string",
          "firstName": "string",
          "gender": "MALE",
          "jobTitle": "string",
          "lastName": "string",
          "mobileNumber": "string",
          "number": 0,
          "pet": true,
          "telephone": "string",
          "usTax": true,
          "isPet": true,
          "isUsTax": true
        }
      ],
      "groupInfo": {
        "subsidiary": true,
        "parentCompanyName": "string",
        "address": "string"
      },
      "ubos": [
        {
          "firstName": "string",
          "pet": true,
          "usTax": true,
          "lastName": "string",
          "address": "string",
          "share": 0,
          "isPet": true,
          "isUsTax": true
        }
      ],
      "parentUbos": [
        {
          "firstName": "string",
          "pet": true,
          "usTax": true,
          "lastName": "string",
          "address": "string",
          "share": 0,
          "isPet": true,
          "isUsTax": true
        }
      ],
      "estimationVolume": {
        "currency": "string",
        "averageLoadingPerCard": 0,
        "expectedNumberOfCards": 0,
        "expectedNumberOfLoadingPerMonth": "string",
        "loadingFrequency": "string",
        "cardHolderResidences": [
          {
            "country": "string",
            "rate": 0
          }
        ]
      },
      "bankAccounts": [
        {
          "aba": "string",
          "accountName": "string",
          "accountNumber": "string",
          "achRoutingNumber": "string",
          "address": {
            "addressLine1": "string",
            "addressLine2": "string",
            "city": "string",
            "country": "string",
            "state": "string",
            "zipCode": "string"
          },
          "bankAddress": "string",
          "bankName": "string",
          "beneficiaryName": "string",
          "creationTime": 0,
          "currency": "string",
          "ibanNumber": "string",
          "id": "string",
          "lastUpdatedTime": 0,
          "sortCode": "string",
          "swiftCode": "string",
          "tenantId": "string"
        }
      ],
      "cardAllocations": [
        {
          "cardId": "string",
          "partialCardNumber": "string",
          "externalCardProgram": "string",
          "additionalCardInfo": {
            "date": "string",
            "sendingMethod": "string",
            "trackNumber": "string"
          }
        }
      ]
    }
  ],
  "pageIndex": 0,
  "totalElements": 0,
  "totalPages": 0
}
```

search funding account details

### HTTP Request

`GET BaseUrl + /api/v1/tenants/`

### Query Parameters

Parameter | Description
--------- | -----------
statuses | ACTIVE / INACTIVE
roles | Provide multiple values in new lines.
userPartners | Provide multiple values in new lines  
keyword | search term
pageIndex | integer, page number
pageSize | integer, no of items in a page
assignedCorporate | boolean
isCardholderHoldingCard | boolean 


## Get Tenants 



```shell
curl "BaseUrl + /api/v1/tenants/{tenantId}"
  -H "Authorization: bearer jwttoken"
```



> The above command returns below response

```JSON
{
  "id": "string",
  "name": "string",
  "status": "string",
  "companyKey": "string",
  "domainName": "string",
  "themeCss": "string",
  "logoUrl": "string",
  "companyLegalName": "string",
  "companyTradingName": "string",
  "kyb": "string",
  "preferredLanguage": "string",
  "passwordRegex": "string",
  "businessAddressLine1": "string",
  "businessAddressLine2": "string",
  "businessZipcode": "string",
  "businessCity": "string",
  "businessCountry": "string",
  "phoneNumber": "string",
  "description": "string",
  "verificationProcess": "string",
  "cardProgramTypes": [
    "string"
  ],
  "photoOfInCorporateCerfUrl": "string",
  "photoOfGoodStandingCerfUrl": "string",
  "shippingAddresses": [
    {
      "addressLine1": "string",
      "addressLine2": "string",
      "city": "string",
      "country": "string",
      "emailAddress": "string",
      "firstName": "string",
      "id": "string",
      "isDefault": true,
      "lastName": "string",
      "nickName": "string",
      "phoneNumber": "string",
      "state": "string",
      "zipCode": "string"
    }
  ],
  "logo": {
    "fileName": "string",
    "removed": true,
    "data": "string",
    "url": "string",
    "isRemoved": true
  },
  "photoOfInCorporateCerf": {
    "fileName": "string",
    "removed": true,
    "data": "string",
    "url": "string",
    "isRemoved": true
  },
  "photoOfGoodStandingCerf": {
    "fileName": "string",
    "removed": true,
    "data": "string",
    "url": "string",
    "isRemoved": true
  },
  "documents": [
    {
      "fileName": "string",
      "removed": true,
      "data": "string",
      "url": "string",
      "isRemoved": true
    }
  ],
  "prefundingAccounts": [
    {
      "tenantId": "string",
      "currency": "string",
      "balance": 0,
      "reference": "string"
    }
  ],
  "activePrefundingAccounts": [
    "string"
  ],
  "cardPrograms": [
    {
      "commission": 0,
      "commissionType": "PROFIT_SHARE",
      "creationTime": "2019-04-24T06:22:55.072Z",
      "currency": "string",
      "deleted": true,
      "externalCardProgramCurrencies": "string",
      "externalCardProgramId": "string",
      "id": "string",
      "lastUpdatedTime": "2019-04-24T06:22:55.072Z",
      "name": "string",
      "tenantId": "string",
      "tenantName": "string",
      "termAndCondition": {
        "description": "string",
        "id": "string",
        "name": "string",
        "url": "string"
      }
    }
  ],
  "numberOfActiveCardholders": 0,
  "numberOfPendingCardholders": 0,
  "contacts": [
    {
      "birthDate": "2019-04-24",
      "emailAddress": "string",
      "firstName": "string",
      "gender": "MALE",
      "jobTitle": "string",
      "lastName": "string",
      "mobileNumber": "string",
      "number": 0,
      "pet": true,
      "telephone": "string",
      "usTax": true,
      "isPet": true,
      "isUsTax": true
    }
  ],
  "groupInfo": {
    "subsidiary": true,
    "parentCompanyName": "string",
    "address": "string"
  },
  "ubos": [
    {
      "firstName": "string",
      "pet": true,
      "usTax": true,
      "lastName": "string",
      "address": "string",
      "share": 0,
      "isPet": true,
      "isUsTax": true
    }
  ],
  "parentUbos": [
    {
      "firstName": "string",
      "pet": true,
      "usTax": true,
      "lastName": "string",
      "address": "string",
      "share": 0,
      "isPet": true,
      "isUsTax": true
    }
  ],
  "estimationVolume": {
    "currency": "string",
    "averageLoadingPerCard": 0,
    "expectedNumberOfCards": 0,
    "expectedNumberOfLoadingPerMonth": "string",
    "loadingFrequency": "string",
    "cardHolderResidences": [
      {
        "country": "string",
        "rate": 0
      }
    ]
  },
  "bankAccounts": [
    {
      "aba": "string",
      "accountName": "string",
      "accountNumber": "string",
      "achRoutingNumber": "string",
      "address": {
        "addressLine1": "string",
        "addressLine2": "string",
        "city": "string",
        "country": "string",
        "state": "string",
        "zipCode": "string"
      },
      "bankAddress": "string",
      "bankName": "string",
      "beneficiaryName": "string",
      "creationTime": 0,
      "currency": "string",
      "ibanNumber": "string",
      "id": "string",
      "lastUpdatedTime": 0,
      "sortCode": "string",
      "swiftCode": "string",
      "tenantId": "string"
    }
  ],
  "cardAllocations": [
    {
      "cardId": "string",
      "partialCardNumber": "string",
      "externalCardProgram": "string",
      "additionalCardInfo": {
        "date": "string",
        "sendingMethod": "string",
        "trackNumber": "string"
      }
    }
  ]
}


```

get details of a funding account

### HTTP Request

`GET BaseUrl + /api/v1/tenants/<tenantId>`

### Query Parameters

Parameter | Description
--------- | -----------
tenantId | tenant/funding account  id




## Search PreFunding Transactions


```shell
curl "BaseUrl + /api/v1/pre-funding-transactions/search"
  -H "Authorization: bearer jwttoken"
```



> The above command returns 

```JSON
{
  "limit": 0,
  "offset": 0,
  "results": [
    {}
  ],
  "total": 0
}
```

search pre funding account transactions

### HTTP Request

`POST BaseUrl + /api/v1/pre-funding-transactions/search`

### Query Parameters

Parameter | Description
--------- | -----------
transactionSearchParams | input body check below JSON

``JSON
{
  "source": {},
  "tenantIds": {},
  "target": {},
  "description": {},
  "transTypes": {},
  "transStatuses": {},
  "fromDate": {},
  "toDate": {},
  "tenantId": {},
  "userId": {},
  "offset": {},
  "limit": {},
  "currencyCode": {}
}
``


## Export PreFunding Transactions



```shell
curl "BaseUrl + /api/v1/pre-funding-transactions/search/export/{fileExtension}"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```
```

Export pre funding account transactions list as pdf,excel,csv,web

### HTTP Request

`POST BaseUrl + /api/v1/pre-funding-transactions/search/export/<fileExtension>`

### Query Parameters

Parameter | Description
--------- | -----------
fileExtension | file extension pdf or excel or csv or web
transactionSearchParams | input body check below JSON

``JSON
{
  "source": {},
  "tenantIds": {},
  "target": {},
  "description": {},
  "transTypes": {},
  "transStatuses": {},
  "fromDate": {},
  "toDate": {},
  "tenantId": {},
  "userId": {},
  "offset": {},
  "limit": {},
  "currencyCode": {}
}
``

# Manage cardholders


## Multi Balances


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/multi-balances"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-24T06:22:53.881Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-24T06:22:53.881Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

get balances in all currencies under a card

### HTTP Request

`GET BaseUrl + /api/v1/cards/{cardId}/multi-balances`

### Query Parameters

Parameter | Description
--------- | -----------
cardId | card Id




## Card-info2


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/card-info2"
  -H "Authorization: bearer jwttoken"
```

> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-26T05:36:09.662Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-26T05:36:09.662Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

get details of a card

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>/card-info2`

### Query Parameters

Parameter | Description
--------- | -----------
cardId | card Id

## Card Status


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/status"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-24T06:22:53.929Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-24T06:22:53.929Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

get status of a card from PEX

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>/status`

### Query Parameters

Parameter | Description
--------- | -----------
cardId | card Id


## Get Card Details 


```shell
curl "BaseUrl + /api/v1/cards/{cardId}"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-24T06:22:53.624Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-24T06:22:53.624Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

get details of a card

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>`

### Query Parameters

Parameter | Description
--------- | -----------
cardId | card Id


## Get Balance of a Card 


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/balance"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-24T06:22:53.647Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-24T06:22:53.647Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

Get a single currency balance of a card account

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>/balance`

### Query Parameters

Parameter | Mandatory | Description
--------- | -------- | -----------
cardId | true | card Id 
currency | true | currency code as query param

## Credit fund to a card account


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/credit-fund"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-24T06:22:53.707Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-24T06:22:53.707Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

Credit fund to a card account

### HTTP Request

`POST BaseUrl + /api/v1/cards/<cardId>/credit-fund`

### Post Parameters

Parameter | Description
--------- | -----------
cardId | card Id
cardCreditRequest | JSON body like below
``JSON
{
  "amount": 0,
  "currency": "string",
  "grossAmount": 0,
  "verificationCode": "string"
}
``



## Get card latest transaction history


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/latest-transaction-history"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 

```JSON
[
  {
    "amount": 0,
    "authorizationIdResp": "string",
    "cardAcceptorNameLoc": "string",
    "currency": "string",
    "dateTime": "string",
    "record": 0,
    "terminalId": "string",
    "transTypeIndicator": "string",
    "transactionType": "string"
  }
]
```

Get latest transaction history of a card account

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>/latest-transaction-history`

### Parameters

Parameter | Description
--------- | -----------
cardId | card Id
currency | currency code as query param



## Change card status V2


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/status-v2"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK

```
```

change Card status from active to inactive or vice versa.

### HTTP Request

`PUT BaseUrl + /api/v1/cards/<cardId>/status-v2`

### Parameters

Parameter | Description
--------- | -----------
cardId | card Id
statusCode | query param, supported action codes :- "1","2", "3", "4", "5", "6", "7", "8"



## Card replacement


```shell
curl "BaseUrl + /api/v1/cards/{oldCardId}/card-replacement/{newCardId}"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-26T05:36:09.766Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-26T05:36:09.766Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

Replace an old card with a new card

### HTTP Request

`PUT BaseUrl + /api/v1/cards/<oldCardId>/card-replacement/<newCardId>`

### Parameters

Parameter | Description
--------- | -----------
cardId | card Id 
newCardId | new card Id


## Get Card transaction list


```shell
curl "BaseUrl + /api/v1/cards/{cardId}/transaction-list"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
[
  {
    "arn": "string",
    "bilCurrency": "string",
    "billAmnt": "string",
    "cardNumberAccNum": "string",
    "cnt": "string",
    "contractType": "string",
    "feeAmnt": "string",
    "merchantCity": "string",
    "merchantCountry": "string",
    "merchantCountryCode": "string",
    "merchantId": "string",
    "merchantName": "string",
    "oifBillCur": "string",
    "oifStllCur": "string",
    "origin": "string",
    "postedAmnt": "string",
    "refNumber": "string",
    "settlement": "string",
    "sttlAmnt": "string",
    "sttlCurrency": "string",
    "terminalId": "string",
    "trace": "string",
    "transactionAmnt": "string",
    "transactionCode": "string",
    "transactionCurrency": "string",
    "transactionType": "string",
    "tranxDate": "string",
    "tranxId": "string",
    "tranxInd": "string",
    "tranxTime": "string"
  }
]
```

get transaction list of a card 

### HTTP Request

`GET BaseUrl + /api/v1/cards/<cardId>/transaction-list`

### Parameters

Parameter | Description
--------- | -----------
cardId | card Id 
currency | currency
from | from date
to | to date




## Get Card Stock


```shell
curl "BaseUrl + /api/v1/card-stock?cardProgramId=abd3435akadk12"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
[
  {
    "additionalCardInfo": {
      "date": "string",
      "sendingMethod": "string",
      "trackNumber": "string"
    },
    "allocatedToTenant": {
      "id": "string",
      "name": "string"
    },
    "assignedToCardHolder": true,
    "cardStockId": "string",
    "expiredDate": "string",
    "externalCardProgramId": "string",
    "partialCardNumber": "string"
  }
]
```

get a list of available cards based on program id

### HTTP Request

`GET BaseUrl + /api/v1/card-stock?cardProgramId=`

### Query Parameters

Parameter | Description
--------- | -----------
cardProgramId | Card Program Id




## Search Card Stock


```shell
curl "BaseUrl + /api/v1/card-stock/search"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
{
  "limit": 0,
  "offset": 0,
  "results": [
    {}
  ],
  "total": 0
}
```

search card from a stock with a keyword

### HTTP Request

`POST BaseUrl + /api/v1/card-stock/search`

### Parameters

Parameter | Description
--------- | -----------
cardStockSearchParams | In JSON format like below.
``JSON
{
  "cardStockIds": {},
  "cardNumberLastDigits": {},
  "tenantIds": {},
  "assignedToCardHolder": {},
  "offset": {},
  "limit": {}
}
``


## Search Card


```shell
curl "BaseUrl + /api/v1/card/search"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
{
  "limit": 0,
  "offset": 0,
  "results": [
    {}
  ],
  "total": 0
}
```

search the card by CardHolderId, CardProgramIds,externalCardProgramIds, CardIds, CardNumber  etc...

### HTTP Request

`POST BaseUrl + /api/v1/card/search`

### Parameters

Parameter | Description
--------- | -----------
cardSearchParams | In JSON format like below.

``
{
  "cardHolderId": {},
  "cardProgramIds": {},
  "externalCardProgramIds": {},
  "cardIds": {},
  "cardNumber": {},
  "balance": {},
  "nameOnCard": {},
  "expiredDate": {},
  "cardStatusCodes": {},
  "fromCreationDate": {},
  "toCreationDate": {},
  "thirdPartyType": {},
  "currencyCodes": {},
  "tenantIds": {},
  "allocatedTenantIds": {},
  "userRoleIds": {},
  "assignedToCardHolder": {},
  "offset": {},
  "limit": {}
}
``


## Get External CardPrograms


```shell
curl "BaseUrl + /api/v1/cardPrograms/external"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
[
  {
    "activated": true,
    "cardProgramId": "string",
    "cardProgramName": "string",
    "createdBy": "string",
    "createdOn": "2019-04-29T06:41:13.394Z",
    "currency": "string",
    "description": "string",
    "shared": true,
    "startingNumber": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  }
]
```

Get the external cardprogram details,This is the card program of PEX

### HTTP Request

`GET BaseUrl + /api/v1/cardPrograms/external`

### Parameters

Parameter | Description
--------- | -----------
cardProgramId | card program id


## Update Card Status


```shell
curl "BaseUrl + /api/v1/card/{cardId}/status"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```JSON
{
  "additionalCardInfo": {
    "date": "string",
    "sendingMethod": "string",
    "trackNumber": "string"
  },
  "allocatedToTenant": {
    "id": "string",
    "name": "string"
  },
  "amountLimit": 0,
  "assignedToCardHolder": true,
  "balances": [
    {
      "balance": 0,
      "currency": "string"
    }
  ],
  "batchReferenceId": 0,
  "cardEstimatedUsage": {
    "yearlyAtmWithdrawal": "string"
  },
  "cardHolder": {
    "address2": "string",
    "address3": "string",
    "address4": "string",
    "address5": "string",
    "applicationId": "string",
    "billingAddress1": "string",
    "billingAddress2": "string",
    "billingAddress3": "string",
    "billingAddress4": "string",
    "billingAddress5": "string",
    "billingCity": "string",
    "billingCountry": "string",
    "billingState": "string",
    "billingZipOrPostalCode": "string",
    "cellNumber": "string",
    "cellPhoneProvider": "string",
    "citizenCountry": "string",
    "city": "string",
    "country": "string",
    "dob": "string",
    "drivingLicense": "string",
    "drivingLicenseNumber": "string",
    "drivingLicenseState": "string",
    "email": "string",
    "employmentStatus": "string",
    "firstName": "string",
    "firstName2": "string",
    "firstName3": "string",
    "foreignCountryCode": "string",
    "foreignID": "string",
    "foreignIDType": "string",
    "gender": "MALE",
    "id": "string",
    "langId": "string",
    "lastName": "string",
    "lastName2": "string",
    "lastName3": "string",
    "middleName": "string",
    "middleName2": "string",
    "middleName3": "string",
    "motherMaidenName": "string",
    "nameofEmployer": "string",
    "occupation": "string",
    "postalCode": "string",
    "relation": "string",
    "residentialPhone": "string",
    "shipToFirstName": "string",
    "shipToLastName": "string",
    "shipToMiddleName": "string",
    "shippingAddressOptionId": "string",
    "ssn": "string",
    "stateCode": "string",
    "status": "string",
    "workPhone": "string"
  },
  "cardId": "string",
  "cardNote": "string",
  "cardNumber": 0,
  "cardNumberLastDigits": "string",
  "cardProgram": {
    "commission": 0,
    "commissionType": "PROFIT_SHARE",
    "creationTime": "2019-04-29T06:41:13.559Z",
    "currency": "string",
    "deleted": true,
    "externalCardProgramCurrencies": "string",
    "externalCardProgramId": "string",
    "id": "string",
    "lastUpdatedTime": "2019-04-29T06:41:13.559Z",
    "name": "string",
    "tenantId": "string",
    "tenantName": "string",
    "termAndCondition": {
      "description": "string",
      "id": "string",
      "name": "string",
      "url": "string"
    }
  },
  "cardProgramId": "string",
  "cardReferenceID": 0,
  "cardShippingMethodId": 0,
  "cardStatusCode": "VALID_CARD",
  "creationTime": "string",
  "customerId": "string",
  "deposit": 0,
  "existingCardNo": "string",
  "existingCardReferenceID": "string",
  "expiryDate": "string",
  "externalCardProgramId": "string",
  "nameOnCard": "string",
  "partialCardNumber": "string",
  "primaryCardNo": "string",
  "primaryCardReferenceID": "string",
  "referenceId": 0,
  "shippingAddress": {
    "addressLine1": "string",
    "addressLine2": "string",
    "city": "string",
    "country": "string",
    "emailAddress": "string",
    "firstName": "string",
    "id": "string",
    "isDefault": true,
    "lastName": "string",
    "nickName": "string",
    "phoneNumber": "string",
    "state": "string",
    "zipCode": "string"
  },
  "startingNumbers": "string",
  "thirdPartyType": "I2C",
  "withdrawAmount": 0
}
```

Change status of a card account

### HTTP Request

`PUT BaseUrl + /api/v1/card/{cardId}/status`

### Parameters

Parameter | Description
--------- | -----------
cardId | card id
statusCode | statusCode
isForcedPost | boolean




## Logout


```shell
curl "BaseUrl + /api/v1/logout"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```
```

Logout the user from EWM 

### HTTP Request

`POST BaseUrl + /api/v1/logout`






## Resent code


```shell
curl "BaseUrl + /api/v1/resent-code"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```
```

Resent the verification code(OTP) 

### HTTP Request

`POST BaseUrl + /api/v1/resent-code`



## Verify


```shell
curl "BaseUrl + /api/v1/verify"
  -H "Authorization: bearer jwttoken"
```


> The above command returns 200 OK on success

```
```

This API is used to verify OTP while login. 

### HTTP Request

`POST BaseUrl + /api/v1/verify`

### Parameters

Parameter | Description
--------- | -----------
verificationCodeRequest | In JSON format like below.

``
{
  "code": "string"
}
``