# Creating the request

Requests to the API are over the standard HTTP \(HyperText Transfer Protocol\). The protocol defines three parts to every request.

1. the method/uri header
2. a number of request headers
3. optional body of the request

`Note also that the HTTP request also needs to be secured by a TLS/SSL connection, often referred to as HTTPS (or HTTP over SSL). iVvy uses industry standard TLS (Transport Layer Security, the successor to SSL, Secure Sockets Layer) to secure the HTTP transport to the API to ensure eavesdropping on the connection by third parties is protected.`

