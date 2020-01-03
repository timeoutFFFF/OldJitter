
**OldJitter**

OldJitter is ChakraCore based exploit challenge used as the *Exploit 400* challenge in TrendMicroCTF 2019. 

Directory Structure:

- PoCs: contains JS exploit code which successfully gets the flag.
- Challenge: contains the OldJitter challenge.  

Even though the challenge was easy from a development perspective, but I made 2 mistakes while developing this simple challenge. 
 
First, some participants knew a trick to read the file from the system (without exploitation). The interesting thing is the first 5-6 teams obtain the flag using such trick and remaining teams, who successfully submitted the flag, got the flag by exploiting the vulnerability.

The example of such JS code is as follows:

Payload-1: 
```
print((WScript.LoadTextFile('/home/ctf/flag')));.
```

Payload-2:
```
console.log(read("/home/ctf/flag"));
```

I was not knowing this so I didn't test during the development phase.

The second mistake was Security101 mistake. I didn't set the permission of the files correctly. Check `exploit9.js` to see how my mistake was exploited. The good thing was I was running 2 instances of service and monitoring the traffic which gave me time to fix my mistake.




Some solution write-up:

- https://gist.github.com/itszn/3277e8aa56c91f8296d88d25d96df717 
- https://balsn.tw/ctf_writeup/20190906-trendmicroctfqual/#400
- https://theromanxpl0it.github.io/articles/2019/09/09/Trend-Micro-CTF-ChakraCore-JIT-exploitation.html


Special thanks to [zebasquared](https://twitter.com/zebasquared) 
