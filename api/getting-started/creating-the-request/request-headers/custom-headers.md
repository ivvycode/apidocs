# Custom Headers

A number of custom headers can be used with the request to the API.

## IVVY-Date \(Optional\)

If your HTTP client does not allow the date header to be accessed or set, you can optionally use this header to use for the date string. Note if this header is used, the ‘date’ part of the [signed string](../signing-the-request.md) will need to be empty. The format of the value of this header will be the[ iVvy Timestamp Format](../../../development-reference/timestamp-format.md), NOT the string format of the standard Date header.

## X-Api-Authorization \(Required\)

This is the same format at the standard HTTP Authorization header. For iVvy requests, the format is...

`X-Api-Authorization: IWS key:signature`

… where IWS is the authentication system used by iVvy, key is the key used to sign the request, and the signature is the HMAC-SHA1 signature of the request. See [Signing the request](../signing-the-request.md) for details on how to sign a request.

The iVvy API server will lookup the secret key associated with the key used in this header, then use the details in the request in association with the secret key, then reconstruct the [HMAC-SHA1](../../../development-reference/hmac-sha1.md) hash. Only when the calculated hash, and the signature sent through this header match will the request be authenticated.

