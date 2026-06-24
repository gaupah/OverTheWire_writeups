![alt text](image.png)

[Challenge Page](https://overthewire.org/wargames/bandit/bandit9.html)

Helpful Reading Material:

[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

### The goal:
- Log in in as `bandit8`. The password is in `data.txt`, but this time there's no keyword to search for. 
- The clue is that the password is the **only line of text that occurs exactly once**. Every other line is a **duplicate**. We need to find the **unique one**.

### A lil bit of theory:
Two new tools this level:

- `sort` : sorts lines of text alphabetically (or numerically). By itself not super exciting, but crucial here.

- `uniq` : filters out duplicate lines. The catch is that it only detects duplicates that are adjacent (right next to each other). If the same line appears at the top and bottom of the file with different lines in between, `uniq` won't catch it as a duplicate.

That's why `sort` has to come first, it groups all identical lines together so `uniq` can actually do its job.


The flag relevant here:

`-u` : only print lines that appear exactly once (unique lines)


### My approach:
SSH'd into the server as bandit8
```
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
![alt text](image-1.png)

Checked the current directory and the files in it:
```
pwd
ls -la
```

There's data.txt. First thing, I checked what `uniq` can do:

```
man uniq
```
![alt text](image-2.png)

In my first attempt:
```
cat data.txt | uniq -c 1
```
Got an error, hat's not how -c works, it doesn't take an argument. So, I scrapped that.

Next try:
```
cat data.txt | uniq -u
```
![alt text](image-3.png)
![alt text](image-4.png)

That gave a massive list of line. That's because `uniq` only removes adjacent duplicates. The file isn't sorted, so identical lines scattered throughout the file all look "unique" to `uniq`. 
It's just doing its job wrong because I didn't set it up properly.

Checked what `sort` can do using:
```
man sort
```
![alt text](image-5.png)

![alt text](image-6.png)

Then tried running the following command to see how if plays out with the file:
```
cat data.txt | sort -u
```
It showed all the lines, but sorted chronolically.

![alt text](image-7.png)


To fix, sort first so all duplicates are grouped together, then run `uniq -u`:

```
cat data.txt | sort | uniq -u
```
![alt text](image-8.png)

and we got the password!

### The password for the next level (level 9):
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

### Extra discussion:

#### Why did `sort | uniq -u` Work but `uniq -u` alone didn't?

1. `uniq` compares each line to the one immediately above it. 

2. If duplicates are spread out across the file, `uniq` sees them as separate because they're never adjacent.

3. `sort` fixes this by pulling all identical lines next to each other first.

4. So when `uniq` runs, every duplicate is sitting right next to its twin, and the one truly unique line stands alone.
