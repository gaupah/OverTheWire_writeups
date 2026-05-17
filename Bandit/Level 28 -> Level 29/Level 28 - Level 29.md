![](<Pasted image 20260517002120.png>)

this challenge looks similar to the last one

![](<Pasted image 20260517002340.png>)
don't forget to add `:2220` after `.org` in the link when cloning the repo (or it will give you an error)

![](<Pasted image 20260517002515.png>)

now this looks like the password was obfuscated

let's try to go through the logs to see if we can find any clues:
![](<Pasted image 20260517002557.png>)


![](<Pasted image 20260517002732.png>)
this might be a clue...fix info leak, maybe we can try checking the code version by accessing the previous commit/rebase

![](<Pasted image 20260517002852.png>)
AHA! There we go

The password for the next level (Level 29) is:
```
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

