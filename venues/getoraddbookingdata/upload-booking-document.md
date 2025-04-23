# Upload Booking Document

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=uploadBookingDocument" %}
{% api-method-summary %}
Upload Booking Document
{% endapi-method-summary %}

{% api-method-description %}
Uploads a venue booking document.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A POST request that represents uploading a booking document to a venue using multipart/form-data. See below for the data description and example request.
{% endapi-method-request %}

{% endapi-method-spec %}
{% endapi-method %}

## Booking Document

| Property | Type | Required | Description |
| :------- | :--- | :------- | :---------- |

| venueId | integer | required | The id of the venue to which the booking note belongs |
| bookingId | integer | required | The id of the booking to which the booking note will be assigned. |
| fileId | string | required | The path of the file to be uploaded |
| type | integer | required | The [type](upload-booking-document.md#booking-document-type) of the booking note. |
| status | integer | required | The [type](upload-booking-document.md#booking-document-status) of the booking note. |

## Example Request

```sh
#!/usr/bin/env bash

# Configuration variables
API_KEY="apikey"
API_SECRET="apkisecret"
API_VERSION="1.0"
API_URL="[PlatformAddress]/api/1.0/venue?action=addOrUpdateBookingNote"

# Get the current date in the required format (UTC timezone)
DATE=$(date -u +"%Y-%m-%d %H:%M:%S")

# Create request data (JSON format)
REQUEST_DATA="{\"venueId\":\"1\",\"bookingId\":\"29836\",\"type\":\"3\",\"status\":\"3\"}"
PATH_TO_FILE="/path/to/document.pdf"

# Compute the MD5 hash of the request data
BODY_MD5=$(echo -n "$REQUEST_DATA" | md5sum | awk '{print $1}')

# Compute the md5 checksum of the file
FILE_MD5=$(md5sum "$PATH_TO_FILE" | awk '{print $1}')

# Construct the URI path
URI_PATH="/api/1.0/venue?action=uploadBookingDocument"

# Set the content-type including the boundary
CONTENT_TYPE="multipart/form-data"

# Prepare the string to sign
STRING_TO_SIGN="POST${BODY_MD5}${FILE_MD5}${CONTENT_TYPE}${URI_PATH}${API_VERSION}ivvydate=${DATE}"
STRING_TO_SIGN="${STRING_TO_SIGN,,}"
echo $STRING_TO_SIGN

# Generate the HMAC signature using the secret key
SIGNATURE=$(echo -n "$STRING_TO_SIGN" | openssl dgst -sha1 -hmac "$API_SECRET" | awk '{print $2}')

# Perform the API call using curl
curl --location "$API_URL" \
  --header "Content-Type: ${CONTENT_TYPE}" \
  --header "X-Api-Authorization: IWS ${API_KEY}:${SIGNATURE}" \
  --header "Content-MD5: ${FILE_MD5}" \
  --header "IVVY-Date: ${DATE}" \
  --header "X-Api-Version: ${API_VERSION}" \
  --form "fileId=@${PATH_TO_FILE}" \
  --form "venueId=1" \
  --form "bookingId=29836" \
  --form "type=3" \
  --form "status=3" \
```

## Returns

| Property | Description                                             |
| :------- | :------------------------------------------------------ |
| success  | Whether or not the booking document was uploaded        |
| id       | The unique id of the booking document that was uploaded |

## Throws

| Code                 | Description                       |
| :------------------- | :-------------------------------- |
| Specific Code: 24458 | The request contains bad data     |
| Specific Code: 24459 | The request contains invalid data |

## Booking Document Type

| Type | Description |
| :--- | :---------- |
| 3    | Quote       |
| 4    | Contract    |
| 5    | Other       |

## Booking Document Status

| Type | Description |
| :--- | :---------- |
| 3    | Draft       |
| 4    | Created     |
| 5    | Sent        |
| 8    | Completed   |
