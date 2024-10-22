# Challenge10: HTTP - Headers

## Solution

1. As the title, this challenge will mainly about request and response headers.
2. First open Burp Suite and open the target site.
3. Send the GET request to repeater and click send request again
4. In the reponse window, there is 1 header:
    
```
Header-RootMe-Admin: none
```
5. Now, before sending previous request, we will add this header into our request:

```
Header-RootMe-Admin: true
```
6. Send this GET request and get the password :)
