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

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

