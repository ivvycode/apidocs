# Get Company List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=getCompanyList" path="" %}
{% api-method-summary %}
Get Company List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of companies
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of companies to get in a single call
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=true %}
The starting result of the page. Not this is zero based \(i.e. sending start = 0 will start from the first result.\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Additional [Filter ](../getting-started/interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| venueId | Filter by specific Venue | integer |
| venueGroupId | Filter by SPecific Venue Group | integer |

## Returns

| Property | Description |
| :--- | :--- |
| id | The unique identifier for the company |
| externalId | Optionally a unique identifier of the company that is managed by an external application |
| businessName | The company's business name |
| tradingName | The company's trading name |
| businessNumber | The company's registration number |
| phone | The company's phone number |
| fax | The company's fax number |
| website | The company's website |
| email | The company's email address |
| address | The company’s address. This is an an object with the address [keys](get-company-list.md#keys). |
| modifiedDate | The modified date of the company |
| primaryAccountManager | The primary account manager of the company. This is an an object with the [keys](get-company-list.md#primaryaccountmanager) |
| secondaryAccountManager | The secondary account manager of the company. This is an an object with the [keys](get-company-list.md#secondaryaccountmanager) |
| industry | The industry of the company. This is an an object with the [keys](get-company-list.md#industry) |
| primaryContact | The primary contact of the company. This is an an object with the [keys](get-company-list.md#primarycontact) |
| commissionSpace | The commission amount of the company space. |
| commissionSpaceType | The commission amount type of the company space. |
| commissionFoodValue | The commission amount of the company food. |
| commissionFoodType | The commission amount type of the company food. |
| commissionBeverageValue | The commission amount of the company beverage. |
| commissionBeverageType | The commission amount type of the company beverage. |
| commissionAudioVisualValue | The commission amount of the company audio visual. |
| commissionAudioVisualType | The commission amount type of the company audio visual. |
| commissionAccommodationValue | The commission amount of the company accommodation. |
| commissionAccommodationType | The commission amount type of the accommodation. |
| iataNumber | The IATA number of commission payable to the agent. |

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

## primarycontact

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the contact |
| firstName | string | The first name of the contact |
| lastName | string | The last name of the contact |
| email | string | The email address of the contact |
| phone | string | The phone number of the contact |

## primaryaccountmanager

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the primary account manager |
| firstName | string | The first name of the primary account manager |
| lastName | string | The last name of the primary account manager |
| email | string | The email address of the primary account manager |

## secondaryaccountmanager

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the secondary account manager |
| firstName | string | The first name of the secondary account manager |
| lastName | string | The last name of the secondary account manager |
| email | string | The email address of the secondary account manager |

## industry

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the industry |
| name | string | The name of the industry |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

