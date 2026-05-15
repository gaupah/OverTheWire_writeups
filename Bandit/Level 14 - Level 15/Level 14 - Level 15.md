![[Pasted image 20260515213822.png]]

Helpful Reading Material:

- [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (Not completely accurate, but good enough for beginners)
- [IP Addresses](https://computer.howstuffworks.com/web-server5.htm)
- [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
- [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
- [Ports](https://computer.howstuffworks.com/web-server8.htm)
- [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_\(computer_networking\))

![[Pasted image 20260515213849.png]]
**Passwords in unix/linux systems are stored in the /etc/passwd file**

**So we try to read that file:**
![[Pasted image 20260515213914.png]]

![[Pasted image 20260515213930.png]]

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

![[Pasted image 20260515214020.png]]

**Just doing nc localhost 30000 was taking a lot of time to resolve so I just used echo “thepasswd” and piped it to the netcat address**

```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

