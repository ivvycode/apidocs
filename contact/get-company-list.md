# Get Company List

### Description

Get list of companies.

### API URL

`[PlatformAddress]/api/1.0/contact?action=getCompanyList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of companies to get in a single api call | Required | integer |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Required | integer |

### Additional [Filter ](../interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| --- | --- | --- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

### Returns

| Property | Description |
| --- | --- |
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

### Keys

| keys |
| --- |
| line1 |
| line2 |
| line3 |
| line4 |
| city |
| stateCode \(e.g: QLD\) |
| countryCode \(e.g: AU\) |
| postalCode |

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

