# Challenge27: Directory traversal

## Solution

1. Now you need to open Burp Suite, this challenge quite easy :)

2. Now, try to find some hint with clicking the Navbar:
    + Emotes
    + Apps
    + Devices
    + ...

3. Notice the URL path :)):

```
When clicking app:

http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=apps
```

4. So now, we just directly change the path on the URL, like:

```
http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=../
```

5. There will be __galerie__ folder display as an image, now try to go to that folder:

```
http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=../galerie
```

6. Now, you will see all the folder listed on the Navbar and 1 sus folder __86hwnX2r__. Now traverse to that folder :)

7. There will be a password.txt file displayed on the screen but we can not do anything with it even traverse to it.

8. Easiest way is to use the __wget__ cmd to download whole site :)

```
wget -r http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=../galerie
```

9. Go to the password.txt and submit the flag.
