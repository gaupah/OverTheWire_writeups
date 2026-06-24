→![](<Pasted image 20260515225527.png>)

![](<Pasted image 20260515225540.png>)

![](<Pasted image 20260515225552.png>)

The script generates the temp file using: 
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)


Running this command gives:
![](<Pasted image 20260515225613.png>)

**Now appending this to the tmp file path to find the password:**
![](<Pasted image 20260515225629.png>)

```
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

