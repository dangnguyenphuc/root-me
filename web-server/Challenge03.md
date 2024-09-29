# Challenge03: HTTP - Open redirect

## Purpose:
    
    Redirect current link on the webpage to malicious link.

## Solution:
    1. Open Burp Suite
    2. Open the target site
    3. Send the GET request to repeater
    4. Check the facebook link:
    
    ```
    ?url=https://facebook.com?h=...
    ```
    
    5. What is the __h__ parameter stand for ? => After a while, i found out that It's MD5 hash value of "https://facebook.com".
    6. Now, we can redirect to our link by make a GET request:
        + url: https://github.com/dangnguyenphuc/root-me
        + h: MD5 hash(url)
    7. Get password from response.
