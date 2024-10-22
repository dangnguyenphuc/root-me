# Challenge09: HTTP - Directory indexing

# Solution

1. Open url: http://challenge01.root-me.org/web-serveur/ch4/
2. Nothing display on the browser :). We'll try to inspect(F12).
3. After inspecting the html code, there's a line:

```php
include(admin/pass.html)
```

4. Give it a try and browse for that url path: http://challenge01.root-me.org/web-serveur/ch4/admin/pass.html


5. You will get rick roll :)
6. Now try the dirsearch with url: http://challenge01.root-me.org/web-serveur/ch4/admin/
7. You will find the backup folder: http://challenge01.root-me.org/web-serveur/ch4/admin/backup
8. Browse for that backup path, you will see a admin.txt file
9. Open that file and you will get this challenge password. :)
