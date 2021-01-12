# Title of Room/Box

First we start with a nmap scan<br>
*Here we add an ouput of the scan or we add it as a text in ```.<br>
The path of images would be /images/nmap/name_of_the_screenshot*

Since we now know which ports are there here we have 80 and 22 so lets use gobuster.<br>
*Screenshot of gobuster output or use ``` to add them as a text*


We found a place where we can upload files `/upload` so lets try and upload a reverse shell.

After we upload it we try to priv escalate so we get root when we type `sudo -l` we can see that we can use `sudo find`<br>
so lets take a look at gtfobins now we know that we have to use `sudo find . -exec /bin/sh \; -quit` and lets check if we are root.<br>
`whoami`
*Image that we are root*



*This is an example of a writeup for any questions create an issue.*