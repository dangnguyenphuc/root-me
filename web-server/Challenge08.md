# Challenge08: Backup file

## Intuition

What can hacker do if there is backup file in our website path?

## Solution

    1. Install dirsearch
    
```bash
sudo apt install dirsearch
```

    2. Use dirsearch cmd:

```bash
dirsearch -u http://challenge01.root-me.org/web-serveur/ch11/
```

    3. The backup file is: index.php~
