# Add or Update Company

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=addOrUpdateCompany" method="post" summary="Add or Update Company" %}
{% swagger-description %}
Add or update company details
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The company's identifier. (Leave empty to add the company to the system)
{% endswagger-parameter %}

{% swagger-parameter name="externalId" type="string" in="path" %}
Optionally a unique identifier of the company that is managed by an external application
{% endswagger-parameter %}

{% swagger-parameter name="businessName" type="string" in="path" %}
The company's business name. (Mandatory if adding a new company)
{% endswagger-parameter %}

{% swagger-parameter name="tradingName" type="string" in="path" %}
The company's trading name
{% endswagger-parameter %}

{% swagger-parameter name="businessNumber" type="string" in="path" %}
The company's registration number
{% endswagger-parameter %}

{% swagger-parameter name="phone" type="string" in="path" %}
The company's phone number
{% endswagger-parameter %}

{% swagger-parameter name="otherPhone" type="string" in="path" %}
The company's other phone number
{% endswagger-parameter %}

{% swagger-parameter name="fax" type="string" in="path" %}
The company's fax number
{% endswagger-parameter %}

{% swagger-parameter name="website" type="string" in="path" %}
The company's website
{% endswagger-parameter %}

{% swagger-parameter name="email" type="string" in="path" %}
The company's email address
{% endswagger-parameter %}

{% swagger-parameter name="address" type="string" in="path" %}
The company's address.
{% endswagger-parameter %}

{% swagger-parameter name="primaryAccountManagerId" type="integer" in="path" %}
The id of primary account manager of the company
{% endswagger-parameter %}

{% swagger-parameter name="secondaryAccountManagerId" type="integer" in="path" %}
The id of secondary account manager of the company
{% endswagger-parameter %}

{% swagger-parameter name="industryId" type="integer" in="path" %}
The industry id of company
{% endswagger-parameter %}

{% swagger-parameter name="isAgent" type="integer" in="path" %}
Whether the company has an agent or not.
{% endswagger-parameter %}

{% swagger-parameter name="commissionSpace" type="integer" in="path" %}
The commission amount of the company for Space.
{% endswagger-parameter %}

{% swagger-parameter name="commissionSpaceType" type="integer" in="path" %}
The commission amount type of the company for Space.
{% endswagger-parameter %}

{% swagger-parameter name="commissionFood" type="integer" in="path" %}
The commission amount of the company for food.
{% endswagger-parameter %}

{% swagger-parameter name="commissionFoodType" type="integer" in="path" %}
The commission amount type of the company for food.
{% endswagger-parameter %}

{% swagger-parameter name="commissionBeverage" type="integer" in="path" %}
The commission amount of the company for beverage.
{% endswagger-parameter %}

{% swagger-parameter name="commissionBeverageType" type="integer" in="path" %}
The commission amount type of the company for beverage.
{% endswagger-parameter %}

{% swagger-parameter name="commissionAudioVisual" type="integer" in="path" %}
The commission amount of the company for audio visual.
{% endswagger-parameter %}

{% swagger-parameter name="commissionAudioVisualType" type="integer" in="path" %}
The commission amount type of the company for audio visual.
{% endswagger-parameter %}

{% swagger-parameter name="commissionAccommodation" type="integer" in="path" %}
The commission amount of the company for accommodation.
{% endswagger-parameter %}

{% swagger-parameter name="commissionAccommodationType" type="integer" in="path" %}
The commission amount type of the company for accommodation.
{% endswagger-parameter %}

{% swagger-parameter name="iataNumber" type="string" in="path" %}
The IATA number of commission payable to the agent.
{% endswagger-parameter %}

{% swagger-parameter name="updateIfExists" type="boolean" in="path" %}
Whether or not to update the company by businessName when id parameter is missing.
{% endswagger-parameter %}

{% swagger-parameter name="customFields" type="array" in="path" %}
The Company Custom fields
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
Adding a company
{
  "success": true,
  "id": 1618
}

Updating a company
{
  "id": 1618
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request: Adding a company

```javascript
{
  "businessName": "New Company",
  "tradingName": "ABC",
  "email": "company@test.com",
  "address": {
    "line1": "address line 1",
    "line2": "address line 2",
    "stateCode": "QLD",
    "postalCode": "4227",
    "countryCode": "AU"
  },
  "primaryAccountManagerId": 123,
  "secondaryAccountManagerId": 123,
  "industryId": 11,
  "isAgent": 1,
  "commissionSpace": 20,
  "commissionSpaceType" : 2,
  "commissionFoodType": "2",
  "commissionFood":"10",
  "commissionBeverage": 30,
  "commissionBeverageType" : 1,
  "commissionAudioVisual": 50,
  "commissionAudioVisualType" : 2,
  "commissionAccommodation": 50,
  "commissionAccommodationType": 1,
  "iataNumber": "123456789",
  "customFields": [
        {
            "fieldId": 6,
            "value": "2022-08-30 10:00:00 UTC"
        },
        {
            "fieldId": 7,
            "value": "string"
        }
  ]
}
```

## Example Request: Updating a Company

```javascript
{
  "id": 1618,
  "businessName": "Updated Company name",
  "address": {
    "line1": "address line 11",
    "line2": "address line 22",
    "stateCode": "QLD",
    "postalCode": "4227",
    "countryCode": "AU"
  }
  "primaryAccountManagerId": 123,
  "secondaryAccountManagerId": 123,
  "industryId": 11,
  "isAgent": 1,
  "commissionSpace": 20,
  "commissionSpaceType" : 2,
  "commissionFoodType": "2",
  "commissionFood":"10",
  "commissionBeverage": 30,
  "commissionBeverageType" : 1,
  "commissionAudioVisual": 50,
  "commissionAudioVisualType" : 2,
  "commissionAccommodation": 50,
  "commissionAccommodationType": 1,
  "iataNumber": "123456789",
  "customFields": [
        {
            "fieldId": 6,
            "value": "2022-08-30 10:00:00 UTC"
        },
        {
            "fieldId": 7,
            "value": "string"
        }
  ]
}
```

## Keys

| keys                  |
| --------------------- |
| line1                 |
| line2                 |
| line3                 |
| line4                 |
| city                  |
| stateCode (e.g: QLD)  |
| countryCode (e.g: AU) |
| postalCode            |

## Returns

| Property | Description                                      |
| -------- | ------------------------------------------------ |
| success  | If the company was successfully added or updated |
| id       | The unique identifier for the company            |
| message  | Message of the failure (if success was false)    |

This call takes values for a company, and either

1. Updates the values for that company (after you have provided an id in the parameters), or
2. Adds the company to the system (if the id parameter is missing)

The result of this call will contain the status of the result (either true or false) and the company identifier of the updated or newly created company.

The properties of the company currently supported are:

* businessName
* externalId
* tradingName
* businessNumber
* phone
* fax
* website
* email
* address
  * This is an object
* primaryAccountManagerId
* secondaryAccountManagerId
* industryId
* isAgent
* commissionSpace
* commissionSpaceType
* commissionFoodType,
* commissionFood
* commissionBeverage
* commissionBeverageType
* commissionAudioVisual
* commissionAudioVisualType
* commissionAccommodation
* commissionAccommodationType
* iataNumber
* customFields
