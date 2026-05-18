![alt text](image.png)

[Challenge Page](https://overthewire.org/wargames/bandit/bandit3.html)

### Helpful Reading Material:
[Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)

### the goal:
Log in as `bandit2`. The password is in a file called `spaces in this filename` in the home directory. Spaces in the filename. Sounds annoying? it is, believe me. But it's a really common real-world problem, so let's get through it.

### a lil bit of theory:
The shell uses spaces as *delimiters*, meaning when you type cat ```spaces in this filename```, it thinks you're trying to read four separate files called `spaces`, `in`, `this`, and `filename`, none of which exist. 

So we get an error.

There are two clean ways to handle spaces in filenames:

- Quotes — wrap the whole filename in quotes: cat "spaces in this filename"
- Escape characters — put a backslash before each space: cat spaces\ in\ this\ filename

Both work. Pick whichever feels more natural to you.

### my approach:

ssh'd in as `bandit2`:
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
![alt text](image-1.png)

check what's in the home directory:
```
la -la
```

we can see the file: `spaces in this filename`

now this is a bit embarassing, becuase my first few attempts were...not great:

yeah. A lot of failed attempts. The issue was that I kept adding dashes and extensions that weren't part of the actual filename, and cat kept interpreting the leading `--` as flags. The actual filename is just `spaces in this filename` with no dashes or any extension (or any flag to use for `cat`).

the command which worked for me was: 
```
cat -- "spaces in this filename"
```
![alt text](image-2.png)


### the password to login into the next level (level 3):
```
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```



