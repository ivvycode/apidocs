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

{% api-method-parameter name="address" type="string" required=true %}
The company's address. This is an object with the keysstateCode, postalCode and countryCode are required when adding a new Company.
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
  }
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

