# Challenge 02: HTTP - IP restriction bypass

## Ref
- Medium: https://medium.com/r3d-buck3t/bypass-ip-restrictions-with-burp-suite-fb4c72ec8e9c

## Solution
    
1. Open Burp Suite.
2. Open target site: http://challenge01.root-me.org/web-serveur/ch68/
3. Send GET request to repeater.
4. In the GET request, add:
```
X-Forwarded-For: 192.168.1.1
```
5. Check the password in the response.

