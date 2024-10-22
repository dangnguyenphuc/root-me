# Challenge12: HTTP - Improper redirect

## Solution

1. Open Burp Suite and make first GET request to: http://challenge01.root-me.org/web-serveur/ch32
2. So it's always redirect to http://challenge01.root-me.org/web-serveur/ch32/login.php
3. Now try to login with some random information:

```
username: admin
password: admin
```

4. Click "Log in" button and burp suite will record that POST request
5. Now, how's about making a POST request to that http://challenge01.root-me.org/web-serveur/ch32/index.php
6. It's work :))). And you can get password from that index page.


=> Aware of redirect problem for all requests.
