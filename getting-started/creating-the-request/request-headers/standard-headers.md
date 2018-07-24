# Standard Headers

## HOST \(Required\)

You will need to verify which region that you wish to integrate with to determine your host. If you are unsure, you can contact the support team for assistance.

For integrations on our AU Servers, the host is: 

* [api.ap-southeast-2.ivvy.com](http://api.ap-southeast-2.ivvy.com/)

For integrations on our US Servers, the host is: 

* [api.us-west-2.ivvy.com](http://api.us-west-2.ivvy.com/)

For integrations on our UK Servers, the host is: 

* [api.eu-west-2.ivvy.com](http://api.eu-west-2.ivvy.com/)

Contact [support@ivvy.com](mailto:support@ivvy.com) if you are unsure which value to use.

## Date \(Required unless using [IVVY-Date header](custom-headers.md#ivvy-date-optional)\)

The date header determines the date the request was made. The iVvy API uses this date, compared to the date of the server to determine if the request is within the time to live setting. \(Currently requests over 5 minutes old are deemed invalid, this value may change in the future.\)

`Date: Thu, 12 Apr 2012 07:17:06 UTC`

## Content-MD5 \(Required\)

This is the md5 sum of the body of the request. This header is used to verify the contents of the body of the request have not been altered during transport. Note that if there is no content in the body, the MD5 for the request must still be calculated. See [Calculating MD5](../../../development-reference/calculating-md5.md) for more details on how to calculate the value for this field.

## Content-Type

The content type of the request body. Valid request types for the api are...

* application/json

## Content-Length

The length of the request body, in bytes.

