# Challenge21: Flask - Unsecure session

## Tools
+ Flask-session-encode/decode: https://github.com/noraj/flask-session-cookie-manager

+ Flask Unsign: https://github.com/Paradoxis/Flask-Unsign/tree/master

## Solution

1. Open Burp Suite and start capturing target site
2. Go to the admin path to get the guest session cookie:

```
http://challenge01.root-me.org:59084/admin
```

3. You can use the Flask-session-encode/decode package above to decode the cookie session. It simply just decode first part before first '.':

```json
{
    "admin": "false",
    "username": "guest"
}
```

4. Now, our mission is to set the "admin" field to "true". To do that, we just need to know secret key to sign after base64Encode it.

5. So based on the challenge's hint (Secret key is weak), we can try to brute force using the Flask Unsign package above:

```bash
pip3 install flask-unsign-wordlist
pip3 install flask-unsign

flask-unsign --unsign --cookie <cookie>
```

6. The secret key is "s3cr3t" - i remembered
7. Use that secret key and Flask-session-encode/decode package to create a new session cookie
8. Use that cookie to make a GET request to /admin and get the flag :) 
