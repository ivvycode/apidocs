# Get Company

{% swagger baseUrl="[PlatformAddress]/api/1.0/contact?action=getCompany" method="post" summary="Get Company" %}
{% swagger-description %}
Get a single company's detail
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The company's identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "id": "25146",
  "businessName": "Test",
  "tradingName": "Test Trading",
  "businessNumber": "1234586",
  "email": "company@test.com",
  "phone": "0455550000",
  "otherPhone": "123456789",
  "fax": "0455550125",
  "website": "www.test.com",
  "address": {
    "line1": "Street Number",
    "line2": "Street Name",
    "line3": "",
    "line4": "",
    "city": "Gold Coast",
    "stateCode": "QLD",
    "countryCode": "AU",
    "postalCode": "4227"
  },
  "customFields": [
      {
          "fieldId": 5,
          "displayName": "Birth Date",
          "value": "1985-03-17 23:00:00 UTC"
      }
  ],
  "primaryAccountManager": "Test User",
  "secondaryAccountManager": "Test User",
  "industry": "Industry Name",
  "primaryContact": "Test User",
  "commissionRoomHireValue": 123,
  "commissionRoomHireType": "CHF",
  "commissionFoodValue": 222,
  "commissionFoodType": "CHF",
  "commissionBeverageValue": 333,
  "commissionBeverageType": "CHF",
  "commissionAudioVisualValue": 444,
  "commissionAudioVisualType": "CHF",
  "commissionAccommodationValue": 555,
  "commissionAccommodationType": "CHF",
  "iataNumber": "123456789"
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get a specific company`

```javascript
{
  "id":6
}
```

## Returns

| Property                     | Description                                                                                                                |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| id                           | The unique identifier for the company                                                                                      |
| externalId                   | Optionally a unique identifier of the company that is managed by an external application                                   |
| businessName                 | The company's business name                                                                                                |
| tradingName                  | The company's trading name                                                                                                 |
| businessNumber               | The company's registration number                                                                                          |
| phone                        | The company's phone number                                                                                                 |
| otherPhone                   | The company's other phone number                                                                                           |
| fax                          | The company's fax number                                                                                                   |
| website                      | The company's website                                                                                                      |
| email                        | The company's email address                                                                                                |
| address                      | The company’s address. This is an an object with the [keys](get-company.md#keys)                                           |
| modifiedDate                 | The modified date of the company                                                                                           |
| primaryAccountManager        | The primary account manager of the company. This is an an object with the [keys](get-company.md#primaryaccountmanager)     |
| secondaryAccountManager      | The secondary account manager of the company. This is an an object with the [keys](get-company.md#secondaryaccountmanager) |
| industry                     | The industry of the company. This is an an object with the [keys](get-company.md#industry)                                 |
| primaryContact               | The primary contact of the company. This is an an object with the [keys](get-company.md#primarycontact)                    |
| isAgent                      | Whether the company is an agent or not. |
| parentCompanyId              | The parent company id of the company |
| leftValue                    | The left value of the node in the tree structure.                    |
| rightValue                   | The right value of the node in the tree structure. |
| depth                        | The depth of this company in the tree structure. |
| rootId                       | The root company id. |
| commissionSpace              | The commission amount of the company space.                                                                                |
| commissionSpaceType          | The commission amount type of the company space.                                                                           |
| commissionFoodValue          | The commission amount of the company food.                                                                                 |
| commissionFoodType           | The commission amount type of the company food.                                                                            |
| commissionBeverageValue      | The commission amount of the company beverage.                                                                             |
| commissionBeverageType       | The commission amount type of the company beverage.                                                                        |
| commissionAudioVisualValue   | The commission amount of the company audio visual.                                                                         |
| commissionAudioVisualType    | The commission amount type of the company audio visual.                                                                    |
| commissionAccommodationValue | The commission amount of the company accommodation.                                                                        |
| commissionAccommodationType  | The commission amount type of the accommodation.                                                                           |
| iataNumber                   | The IATA number of commission payable to the agent.                                                                        |
| customFields | The custom field information for the company. This is an array of fields, each an object with the [keys](get-company.md#custom-fields-keys). |
| externalUrls | This is an array of [ExternalUrl](get-company.md#external-url-field) field objects of the company. |
## Keys

|                       |
| --------------------- |
| **keys**              |
| line1                 |
| line2                 |
| line3                 |
| line4                 |
| city                  |
| stateCode (e.g: QLD)  |
| countryCode (e.g: AU) |
| postalCode            |

## primarycontact

| Property  | Type    | Description                          |
| --------- | ------- | ------------------------------------ |
| id        | integer | The unique identifier of the contact |
| firstName | string  | The first name of the contact        |
| lastName  | string  | The last name of the contact         |
| email     | string  | The email address of the contact     |
| phone     | string  | The phone number of the contact      |

## primaryaccountmanager

| Property  | Type    | Description                                          |
| --------- | ------- | ---------------------------------------------------- |
| id        | integer | The unique identifier of the primary account manager |
| firstName | string  | The first name of the primary account manager        |
| lastName  | string  | The last name of the primary account manager         |
| email     | string  | The email address of the primary account manager     |

## secondaryaccountmanager

| Property  | Type    | Description                                            |
| --------- | ------- | ------------------------------------------------------ |
| id        | integer | The unique identifier of the secondary account manager |
| firstName | string  | The first name of the secondary account manager        |
| lastName  | string  | The last name of the secondary account manager         |
| email     | string  | The email address of the secondary account manager     |

## industry

| Property | Type    | Description                           |
| -------- | ------- | ------------------------------------- |
| id       | integer | The unique identifier of the industry |
| name     | string  | The name of the industry              |

### Custom Fields Keys

| fieldId |
| displayName |
| value |

## External URL Field

An External URL field is an object with the following details.

| Property | Type   | Description                                                                                                                                              |
| -------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ref      | string | The unique reference key of the external URL                                                                                                             |
| url      | string |  The url link (https) scheme eg. https://example.com |
| label    | string |  The label of the URL to display.                                                                                                                         |

## Throws

| Code                 | Description            |
| -------------------- | ---------------------- |
| Specific Code: 24153 | Unable to find company |

The company identifier must be provided to fetch a specific company from the system.
