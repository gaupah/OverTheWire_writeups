![alt text](image.png)

[Challenge Paage](https://overthewire.org/wargames/bandit/bandit4.html)

### the goal:
- login as `bandit3`
- find the password which is stored in a hidden file inside a directory called `inhere`.

### a lil bit of theory:
Hidden files in Linux are files whose names start with a dot i.e. `.` and they don't show up with a plain `ls`. So we need to know how to reveal them.

In Linux, any file or directory prefixed with a `.` is considered hidden. It won't appear in a regular ls listing. To see hidden files, you need the `-a` flag:

```
ls -a      # shows hidden files
ls -la     # shows hidden files WITH full details (permissions, size, owner, etc.)
```



### my approach:
ssh'd in as `bandit2`:
```
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

![alt text](image-1.png)

I checked the home directory and then moved to the `inhere` directory.
```
ls -la

#then:

cd inhere
```

There it is, a hidden file cheekily named `...Hiding-From-You`.  So, let's read it. First attempt, taking the `--` lesson from last level:

```
cat ... '...Hiding-From-You'
```

got an error, the shell tried to interpret `...` as a seperate argument

so to fix it, I just quoted the full filename:
```
cat '...Hiding-From-You'
```

![alt text](image-2.png)

hehehehe the error popped up but it worked!

I used the example from the last exercise to do so (using quotation marks)

### the password to login into the next level (level 4):
```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```