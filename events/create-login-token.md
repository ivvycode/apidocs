# Create Login Token

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=createLoginToken" path="" %}
{% api-method-summary %}
Create Login Token
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="event" type="integer" required=true %}
The event identifier for the contact to be logged in to
{% endapi-method-parameter %}

{% api-method-parameter name="contact" type="integer" required=true %}
The contact identifier to allow the login
{% endapi-method-parameter %}

{% api-method-parameter name="referrer" type="string" required=false %}
Referrer of the request which will be used in validating the token later
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "token":"fc877d1bae56ebc5a8e19b29a3df67de",
  "loginUrl":"http://wired.ivvy.com/event/SQ6EXR/registration/login/token?t=fc877d1bae56ebc5a8e19b29a3df67de&contact=297466"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Example: Request a login token for a contact on an event`

```javascript
{
  "event":15593,
  "contact":297466
}
```

## Description

Creates a login token that can be used to login to an event, on the behalf of a registered contact. This call takes an event identifier and a contact identifier and an optional referrer url to generate a single-use, time restricted token.

The result will be the token and a URL that can be used to redirect the user to have them logged in to view their registration details without the use of a username and password.

If the referrer is provided when creating the token, the browser’s referrer header will also be checked to ensure the request using the token has been redirected from the specific website saved against the token.

## Returns

| Property | Description |
| :--- | :--- |
| token | Single use, time restricted token for the contact to login to the iVvy Event Website |
| loginUrl | The URL that must be used to authenticate the user with the token |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24099 | Unable to generate token |
| Specific Code: 24098 | Unable to find event |

