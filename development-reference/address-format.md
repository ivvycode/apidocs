# Address Format

The iVvy API represents address objects as follows:

| Property | Type | Description |
| :--- | :--- | :--- |
| line1 | string | Line 1 of the address |
| line2 | string | Line 2 of the address |
| line3 | string | Line 3 of the address |
| line4 | string | Line 4 of the address |
| city | string | The city name of the address |
| postalCode | string | The postal code of the address |
| countryCode | string | The country code of the address |
| stateCode | string | The state code of the address |
| stateName | string | Alternatively the state name of the address \(usually when there is no stateCode\) |

The list of country codes & country division codes that iVvy recognises can be found [here](https://github.com/ivvycode/countries).

