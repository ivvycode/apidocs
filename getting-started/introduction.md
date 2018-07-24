# Introduction

The iVvy system is built with flexibility in mind, and this API forms a large part of that promise.

The API described in this document follows an RPC \(Remote Procedure Call\) paradigm. Each RPC method is grouped into a few higher level namespaces to help organise this document in a more logical manner.

iVvy takes security very seriously and the API described in this document has been designed to be as secure as possible.

* All transport has been secured by utilising industry standard TLS
* Key generation can be done first authenticating with the iVvy backend system
* All requests must be signed using the key/secret pair to prove the request was made by a valid key
* All requests have a time limit to avoid future replay attacks

