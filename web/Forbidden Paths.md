### THE CHALLENGE:
```
Can you get the flag?
Here's the website(http://saturn.picoctf.net:52278/).
We know that the website files live in ``/usr/share/nginx/html/`` and the flag is at ``/flag.txt`` but the website is filtering absolute file paths. 
Can you get past the filter to read the flag?
```

The web filters absolute paths, let's try giving relative path

We know that the website files live in ``/usr/share/nginx/html/`` and the flag is at ``/flag.txt``

So we have to climb up 4 directories to get to the directory where flag.txt is present

Input: ``../../../../flag.txt``

**Flag**: picoCTF{7h3_p47h_70_5ucc355_57e411a1}

Challenge link in Pico Gym: https://play.picoctf.org/practice/challenge/270?category=1&originalEvent=70&page=1
