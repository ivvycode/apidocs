# Signing the request

Every request to the API must be signed with the accounts or users API key. Signing the request is obtained by the following pseudo-code:

```javascript
method := POST
contentMd5 := md5(<body of the request>)
contentType := the value of the Content-Type header
contentSign := {contentMd5}{contentType}
date := the date header of the request (i.e. Tue, 03 Apr, 2012 22:23:24 utc)
        NOTE: if using the IVVY-Date header, this field will be empty
requestString := the entire request string used in the request
apiVersion := the api version to use
ivvyHeaders := Concatenated string of all headers starting with IVVY, removing all the
               Dashes (-) and underscore (_) characters in the header, in alphabetical order, joined together with the
               ampersand (&) character
initialStringToSign := {method}{contentSign}{date}{requestString}{apiVersion}{ivvyHeaders}
stringToSign := lowercase version of the initialStringToSign
```

For example, the following request...

```javascript
POST /api/1.0/test?action=ping HTTP/1.0
Host: api.ap-southeast-2.ivvy.com
Date: Tue, 03 Apr 2012 22:23:24 UTC
Content-MD5: a09f600c77a6dbd947db24c61e8935ca
Content-Type: application/json
Content-Length: 18
X-Api-Version: 1.0
X-Api-Authorization: IWS {key:signature here}
IVVY-Date: 2012-04-03 22:23:24
```

```javascript
{
  "example":"body"
}
```

… will require the following string to be signed …

`posta09f600c77a6dbd947db24c61e8935caapplication/json/api/1.0/test?action=ping1.0ivvydate=2012-04-03 22:23:24`

Note the entire string is set to lowercase before signing.

Signing is achieved using the HMAC algorithm, using SHA1 encryption. See [HMAC-SHA1](../../development-reference/hmac-sha1.md) for further details

