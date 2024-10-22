# Challenge13: HTTP - Verb Tampering

## Solution

1. Open Burp Suite
2. First make a GET request to target url: http://challenge01.root-me.org/web-serveur/ch8/
3. You will not get access to the index file except you have authentication information
4. Now base on the challenge's title, we change the request type to POST, DELETE, PUT, ...
5. After a while, when you change request to DELETE, you can bypass the authenticate step.
6. Get the password :)
