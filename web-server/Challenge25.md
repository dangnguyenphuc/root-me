# Challenge25: JWT Introduction

## Knowledge
    - How many components does JWT consist?

```
There are 3 components:
    - Header: Containg 2 part: type of token(JWT) and the signing algorithm being used (such as HMAC SHA256 or RSA).
    - Payload: Containing the claims.
    - Signature: Use algorithm contained in header to calculate the signature. This signature is used to sign this whole jwt.
```

## Tools
- JWT decode: https://jwt.io/introduction
- Base64 decode/encode: https://www.base64decode.org/
    
## Solution
1. Open Burp Suite and start capture the target site.
2. First, we need to get a guest JWT token by clicking __Login as Guest!__.
3. When getting the guest JWT token, copy it and paste to the [JWT decode page](https://jwt.io/introduction)
4. You will see the decoded Header and Payload like this:
```json
Header: 
{
    'type': 'JWT',
    'alg': 'HS256'
}

Payload:
{
    'admin': 'false'
    'username': 'guest'
}
```
5. So our mission is just to change 'false' to 'true'. When i first approach this problem, i just thought about brute force all the secret key in a dictionary to find the secret key. But not even close :))). The approach that they used in this problem is to change the Header:
```json
{
    'type': 'JWT',
    'alg': 'none'
}
``` 
6. When use 'alg': 'none', our signature doesn't need to be verified anymore :).
7. Get the flag and submit it.
