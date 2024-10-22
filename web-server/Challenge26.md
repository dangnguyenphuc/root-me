# Challenge26: XSS - Server Side

* Fun Fact: this challenge took me 2 days to solve it, but it's easy though. I'm just a dummy :))))

## Solution

0. This web is to generate a certificate with your name and your message typed in the message box. 

1. No need to open Burp Suite :)

2. I tried 2 days to inject the message box :). But no matter how you try, the code you typing into that box always return a string. They're absolutely validated.

3. So now, we tried to inject our name :).

4. Sign up with your account. Because we need to read from /flag.txt, then i just thought about using javascript read a file :)).

5. After trying JS for a while, i simply tried to use the html __<p>__ tag to check if it displays in the PDF file or not:

```
<p>bladyzac</p>
```

6. Yeah! It did not display in the PDF file. So now, how can we read flag.txt using html :)))))). Quite Impossible huh ? We just need use __iframe__ tag :)

```
<iframe src="/flag.txt"></iframe>
```

7. Open your PDF certificate and submit the flag.
