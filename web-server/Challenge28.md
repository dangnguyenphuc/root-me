# Challenge28: File upload - Null byte

## Solution
1. This challenge just aims for file naming.

2. At first, i tried to upload a real jpeg file.

3. Capture that uploading POST request in Burp Suite.

4. After failed with naming with null byte in PHP(\0 character), i just thought about null byte character in URL (%00).

```
For example: dang.php%00.jpeg
```

In dang.php%00.jpeg:

```php
<?php
print_r((scandir('.')));
?>
```

5. Then i tried to upload that file and it was successfully uploaded.

6. Now go to the galerie with this name:

```
galerie/<some_string_i_didnt_remember>/dang.php
```

7. Get your flag.
