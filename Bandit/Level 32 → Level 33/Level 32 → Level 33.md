![](<Pasted image 20260517010441.png>)

NOOOOOOOOOOOOOOOOOOOO MAN 
ALL THAT MORE AND SHELL STUFF WAS ALREADY SO FRUSTRATINGGGGGGGGG

t_t

![](<Pasted image 20260517010614.png>)

![](<Pasted image 20260517010627.png>)
<!--explain what an uppercase shell is-->

i don't what this is, but I am going to take a wild guess:

![](<Pasted image 20260517010727.png>)

hmm okay so I have to write in uppercase 

or maybe in this challenge I have to change the shell too

let's check for available commands we can use:
![[Pasted image 20260517010923.png]]


eheheh


typing `$0`, but why exactly you may ask:

The uppercase shell is a custom binary that takes your input and runs `toupper()` on it before passing it to `sh`. So `ls` → `LS`, `man` → `MAN`, etc.

But `$0` is a **shell special variable** — it contains the name of the currently running shell/script. When the uppercase shell passes `$0` to `sh` to execute, `sh` expands `$0` to something like `/bin/sh` and then executes it... spawning a new normal `sh` process.

The key insight is that `$0` after uppercasing is still `$0` — digits and `$` aren't letters so `toupper()` leaves them completely untouched. So it slips through the filter unchanged and gets evaluated as a variable expansion rather than a command name.

<!--explain this in simpler terms, add an illustration too, if need be-->

![](<Pasted image 20260517011144.png>)

![](<Pasted image 20260517011204.png>)
as we can work like we do normally let's get the password

![](<Pasted image 20260517011303.png>)

The password for the next level (level 33) is:
```
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

