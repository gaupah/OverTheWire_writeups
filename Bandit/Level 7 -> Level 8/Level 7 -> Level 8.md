![alt text](image.png)

[Challenge Link](https://overthewire.org/wargames/bandit/bandit8.html)

### the goal: 
- login as `bandit7`
- retrieve the word next to the word 'millionth' from the `data.txt` file.

### theory time:
The challenge hints at a bunch of new tools — grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd. That's a lot. Naturally, the first thing to do is check what some of these actually do:


![alt text](image-2.png)

![alt text](image-3.png)





For this level though, the one we actually need is grep — a tool that searches through text for lines matching a pattern. Give it a keyword and a file, and it'll pull out every line that contains that word.
And to connect cat and grep together, we use a pipe (|) — one of the most fundamental concepts in Linux. A pipe takes the output of one command and feeds it directly as input to the next. So instead of:

- Print the whole file
- Manually search through it...

we do it one shot.

### my approach
ssh'd into the server as `bandit7` using the command (and the entering the password found in previous level)

```
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
![alt text](image-1.png)


checked what's in the home directory:
```
pwd         #to check current directory
ls -la      #to list files in current directory
```

There's `data.txt`, and look at that file size: `4,184,396 bytes`. BRUH. That's a 4MB text file. `cat`-ing it and reading through it manually is not happening.

so the one-line command I used:
```
cat data.txt | grep -i 'millionth'
```

*note*: The `-i` flag makes the search case-insensitive, just to be safe. 

And there's the password sitting right next to the word millionth, exactly like the challenge said.

![alt text](image-4.png)

### the password for the next level (level 8) is:
```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

