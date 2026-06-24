![alt text](image.png)

[Challenge Page](https://overthewire.org/wargames/bandit/bandit5.html)

### the goal:
- login as `bandit4`.
- the password (for the next level) in the `inhere` directory, but there are 10 files in there (-file00 through -file09), and only one of them contains the password in a human-readable format. The rest are binary garbage. 
- we need to find the right one without manually cat-ing all ten.

### a lil bit of theory (nerdy stuff heh):
This is where the `file` command comes in clutch. It tells you what type of data a file contains, regardless of what the filename says. Unlike file extensions (which mean nothing in Linux :P), `file` actually looks at the content and reports back things like:

- ASCII text - human-readable, this is what we want
- data - binary, not readable as text
- ELF 64-bit - executable
...and a bunch of other types

So instead of opening each file blindly, we just run `file` on all of them and look for the one that says ASCII text.

### my approach:

ssh'd into bandit4 (but forgot to take the screenshot), using the command and entering the password found in the previous level:

```
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

checked the current directory I spawned into:
```
pwd
```

checked available repos:
```
ls -la
```

moved into `inhere` dir and checked for the files available:
```
cd inhere/
ls -la
```

Ten files, all named -file00 through -file09, all looking identical from the outside. My first instinct was to try `file` on one of them:

```
file '-file00'
```

ran into an error :(

so apparently the shell ate the `-f` and interpreted it as a flag. Classic dashed filename problem. 

![alt text](image-1.png)

So, I used `./`
```
file ./-file0*
```

![alt text](image-2.png)

- btw, I used `*` as it is a wild card in Linux, which helps to check all files in one shot. 
- so, insted of typing every filename manually, the shell does the work for all files.

found out that `-file07` is the only one with ASCII text.
so, I read the file using 

```
cat ./-file07
```
got the password! ez pz :D

![alt text](image-3.png)

### the password for the next level (level 5):
```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
