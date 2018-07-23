# HMAC-SHA1

## Bash

The openssl package available in most linux distributions include a way of creating the HMAC-SHA1 string from the command line…

```javascript
echo -n "string to sign" | openssl dgst -sha1 -hmac "my secret key"
(stdin)= a993876ea1218921a1c8551923473da7b310dfae
```

## C\#

```javascript
Encoding encoding = Encoding.UTF8;
byte[] secretBytes = encoding.GetBytes(“my secret key”);
HMACSHA1 hmacsha1 = new HMACSHA1(secretBytes);
hmacsha1.ComputeHash(encoding.GetBytes(“string to sign”));
byte[] data = hmacsha1.Hash;
```

## Javascript

Cryptographic functions are available from the CryptJS libaray at [https://code.google.com/p/crypto-js/](https://code.google.com/p/crypto-js/).

```javascript
var stringToSign = “string to sign”;
var secret = “my secret key”;
var signature = CryptoJS.HmacSHA1(stringToSign, secret);
```

## NodeJS

This code assumes you have the crypto-js library installed \(npm install crypto-js\)

```javascript
$ cat hmacsha1.js 
var CryptoJS = require('crypto-js'),
    message = "string to sign",
    secret = "my secret key",
    sig = CryptoJS.HmacSHA1(message, secret);
console.log("" + sig);

$ node hmacsha1.js 
a993876ea1218921a1c8551923473da7b310dfae
```

## Objective-C

HMAC-SHA1 functionality can be be included in IOS code by first adding the CommonCrypto library to your target, and including the following function in your appDelegate \(or appropriate class\)

```javascript
#import <CommonCrypto/CommonDigest.h>
...
+(NSString*) hmac_sha1:(NSString*)input usingSecret:(NSString*)key
{
    const char *cKey = [key UTF8String];
    const char *cInput = [input UTF8String];
    unsigned char digest[CC_SHA1_DIGEST_LENGTH];
    if (cKey == nil || cInput == nil) {
        return @"";
    }
    NSMutableString *output = [NSMutableString stringWithCapacity:CC_SHA1_DIGEST_LENGTH * 2];
    CCHmac(kCCHmacAlgSHA1, cKey, strlen(cKey), cInput, strlen(cInput), digest);
    for (int i = 0; i < CC_SHA1_DIGEST_LENGTH; i++) {
        [output appendFormat:@"%02x", digest[i]];
    }
    return output;
}
...
```

## PHP

Generating the HMAC-SHA1 in PHP can be done using the following code.

```javascript
<?php 
$stringToSign = “string to sign”;
$keySecret = “my secret key”;
$signature = hash_hmac(”sha1”, $stringToSign, $keySecret);
echo $signature;’
?>
```

This will generate an encrypted hash of the string. In this case the string will be

a993876ea1218921a1c8551923473da7b310dfae

## Ruby

Start up the ‘irb’ and try the following

```javascript
irb(main):001:0> require('openssl')
=> true
irb(main):002:0> OpenSSL::HMAC.hexdigest('sha1', 'my secret key', 'string to sign')
=> "a993876ea1218921a1c8551923473da7b310dfae"
```

