# Challenge24: Insecure Code Management

## Intuition
When first hearing "Code Management" term, i immediately thought about git or some SVN :)

## Solution
1. Open Burp Suite and open the target site.
2. Try to traverse for .git folder:
```
http://challenge01.root-me.org/web-serveur/ch61/.git
``` 
3. Indeed, there is .git folder that are enable user to access.
4. Now, we download it :) 
```
wget -r http://challenge01.root-me.org/web-serveur/ch61/.git
```
5. When download the whole folder completely. Now, we need some git skills :)))
```bash
git log --graph # show all previous commits, display all in a graph tree
```

6. In the 3rd commit, you can see they've already change the password but not encrypt it yet.

7. Now, we checkout to that commit:

```bash
git checkout <git_commit_id>
```
8. Review the source code (password in config.php). Get that password and submit it as a flag.
