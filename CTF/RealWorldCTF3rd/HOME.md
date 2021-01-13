Link on CTFtime: [https://ctftime.org/event/1198](https://ctftime.org/event/1198)  
Official URL: [https://realworldctf.com/](https://realworldctf.com/)    


Challenge Details:
- Name: HOME
- Points: 41
- Description: No need to wear a mask at HOME

# Solution  
This challenge does not require much technical skills, I found out what to do purely by instinct. Also, the description is kinda vague. However, something stands out, which is the word `HOME`. 

By looking at the platform, we can see the homepage of the platform is titled as `HOME` as well (Coincidence? I Think Not!). So, we can presume the flag must be hidden somewhere in the homepage. 

![Imgur](https://i.imgur.com/sWvXe0N.png)

In the beginning, I tried to look for flag that could be hidden in the source code. What I did was running `Ctrl + U` to view the source code. This did not get me anywhere. 

Then, I tried to look for all the static files uploaded to the website. I achieved this by running `Ctrl + Shift + I` → `sources`. After going through the files, I noticed an interesting image under the path `realworldctf.com/static/img/signin.baacf08.jpg` . Could this be the path to flag? Let's find out!

![Imgur](https://i.imgur.com/Wb90IJb.png)

This seems like a Python code, and you have 2 options on how to run them.

1. Run directly as Python code, with one additional line
```python
from pwn import *
io = remote('home.realworldctf.com', 1337)
io.interactive() 
```

2. Run via the Linux terminal
```bash
nc home.realworldctf.com 1337
```

Run either one of the methods above and you will get the flag.
