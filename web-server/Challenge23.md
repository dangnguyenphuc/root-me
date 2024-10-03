# Challenge23: HTTP - Cookies

## Solution

    1. Open Burp Suite and go to target URL
    2. Capture GET request when getting all emails
    3. Add 1 more field in header when making request in step 2:

```
Cookie: ch7=admin
```

    4. Send it and get your flag
