# Add or Update Company

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=addOrUpdateCompany" path="" %}
{% api-method-summary %}
Add or Update Company
{% endapi-method-summary %}

{% api-method-description %}
Add or update company details
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The company's identifier. \(Leave empty to add the company to the system\)
{% endapi-method-parameter %}

{% api-method-parameter name="externalId" type="string" required=false %}
Optionally a unique identifier of the company that is managed by an external application
{% endapi-method-parameter %}

{% api-method-parameter name="businessName" type="string" required=false %}
The company's business name. \(Mandatory if adding a new company\)
{% endapi-method-parameter %}

{% api-method-parameter name="tradingName" type="string" required=false %}
The company's trading name
{% endapi-method-parameter %}

{% api-method-parameter name="businessNumber" type="string" required=false %}
The company's registration number
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=false %}
The company's phone number
{% endapi-method-parameter %}

{% api-method-parameter name="fax" type="string" required=false %}
The company's fax number
{% endapi-method-parameter %}

{% api-method-parameter name="website" type="string" required=false %}
The company's website
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
The company's email address
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
The company's address.
{% endapi-method-parameter %}

{% api-method-parameter name="primaryAccountManagerId" type="integer" required=false %}
The id of primary account manager of the company
{% endapi-method-parameter %}

{% api-method-parameter name="secondaryAccountManagerId" type="integer" required=false %}
The id of secondary account manager of the company
{% endapi-method-parameter %}

{% api-method-parameter name="industryId" type="integer" required=false %}
The industry id of company
{% endapi-method-parameter %}

{% api-method-parameter name="isAgent" type="integer" required=false %}
Whether the company has an agent or not.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionSpace" type="integer" required=false %}
The commission amount of the company for Space.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionSpaceType" type="integer" required=false %}
The commission amount type of the company for Space.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionFood" type="integer" required=false %}
The commission amount of the company for food.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionFoodType" type="integer" required=false %}
The commission amount type of the company for food.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionBeverage" type="integer" required=false %}
The commission amount of the company for beverage.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionBeverageType" type="integer" required=false %}
The commission amount type of the company for beverage.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionAudioVisual" type="integer" required=false %}
The commission amount of the company for audio visual.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionAudioVisualType" type="integer" required=false %}
The commission amount type of the company for audio visual.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionAccommodation" type="integer" required=false %}
The commission amount of the company for accommodation.
{% endapi-method-parameter %}

{% api-method-parameter name="commissionAccommodationType" type="integer" required=false %}
The commission amount type of the company for accommodation.
{% endapi-method-parameter %}

{% api-method-parameter name="updateIfExists" type="boolean" required=false %}
Whether or not to update the company by businessName when id parameter is missing.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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
  "commissionAccommodationType": 1
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
  "commissionAccommodationType": 1
}
```

## Keys

| keys |
| :--- |
| line1 |
| line2 |
| line3 |
| line4 |
| city |
| stateCode \(e.g: QLD\) |
| countryCode \(e.g: AU\) |
| postalCode |

## Returns

| Property | Description |
| :--- | :--- |
| success | If the company was successfully added or updated |
| id | The unique identifier for the company |
| message | Message of the failure \(if success was false\) |

This call takes values for a company, and either

1. Updates the values for that company \(after you have provided an id in the parameters\), or
2. Adds the company to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the company identifier of the updated or newly created company.

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

