# Challenge20: File upload - MIME type

## Solution

    1. Open Burp Suite and go to target site.
    2. Go to upload/
    3. Use image file used in Challenge19 (Double extension) to upload
    4. Upload it and capture the request, then send that request to repeater
    5. In that request, change:

```
Content-type: image/png

or 

Content-type: image/jpeg
```

    6. Send request again and get your flag

