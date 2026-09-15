# Calculating md5

The body of the request must have an MD5 hash calculated to ensure the body has not been altered during transport. It is important this is calculated the same as the iVvy API server to ensure the signature is calculated correctly and the request is authorized.

## Bash \(Linux Command Line\)

```javascript
$ echo -e "string to hash" | md5sum
2fcc83d76f9b2d8ef372271d807a3364  -
```

`Note that any white space either side of the string will also be hashed, creating a different hash`

```javascript
$ echo -e "    string to hash    " | md5sum
6b9202a3b05bd22803fe54767b30ee10  -
```

It is important you strip off any whitespace before hashing the string.

`Note also it is possible to hash an empty string (in the case there is no body in the request).`

```javascript
$ echo -e -n "" | md5sum 
d41d8cd98f00b204e9800998ecf8427e  -
```

## C\

Convert a string to a MD5 hash

```javascript
static private string GetMd5Hash(string input) {
    MD5 md5Hash = MD5.Create();
    byte[] data = md5Hash.ComputeHash(Encoding.UTF8.GetBytes(input));
    return ByteToString(data);
}

// Helper function to convert a byte array to a string.
static private string ByteToString(byte[] data) {
    StringBuilder sBuilder = new StringBuilder();
    for (int i = 0; i < data.Length; i++) {
        sBuilder.Append(data[i].ToString("x2"));
    }
    return sBuilder.ToString();
}
```

## Java

```javascript
import java.security.*;
import java.io.File;
import java.io.FileReader;
import java.io.IOException;

public class MD5Test
{
    public static void main (String args[]) throws Exception {
        String s = "string to hash";
        MessageDigest md = MessageDigest.getInstance("MD5");
        byte[] bytesOfMessage = s.getBytes("UTF-8");
        byte[] thedigest = md.digest(bytesOfMessage);
        System.out.println(
            javax.xml.bind.DatatypeConverter.printHexBinary(thedigest).toLowerCase());
    }
}
```

## Javascript

```javascript
<script src="http://crypto-js.googlecode.com/svn/tags/3.1.2/build/rollups/md5.js"></script>

<script>
    var hash = CryptoJS.MD5("string to hash\n");
    alert("" + hash);
</script>
```

## Nodejs

This code assumes you have the crypto-js library installed \(npm install crypto-js\)

```javascript
$ cat md5.js 
var CryptoJS = require('crypto-js');
var hash = CryptoJS.MD5('string to hash\n');
console.log("" + hash);

$ node md5.js 
2fcc83d76f9b2d8ef372271d807a3364
```

## Objective-C

MD5 funcationlity can be be included in IOS code by first adding the CommonCrypto library to your target, and including the following function in your appDelegate \(or appropriate class\)

```javascript
#import <CommonCrypto/CommonDigest.h>
...
+(NSString*) md5:(NSString*)input
{
    const char *cInput = [input UTF8String];
    unsigned char digest[CC_MD5_DIGEST_LENGTH];
    CC_MD5(cInput, strlen(cInput), digest);    
    NSMutableString *output = [NSMutableString stringWithCapacity:CC_MD5_DIGEST_LENGTH * 2];
    for (int i = 0; i < CC_MD5_DIGEST_LENGTH; i++) {
        [output appendFormat:@"%02x", digest[i]];
    }
    return output;
}
...
```

## PHP

```javascript
echo md5('string to hash\n')
```

